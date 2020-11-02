<template>
  <div>
    <div class="row">
      <div class="col-xl-4 col-lg-4 col-md-4"></div>
      <div class="col-xl-4 col-lg-4 col-md-4">
        <div class="large-spacer"></div>
        <b-form style="padding: 1rem">
          <span class="header-styles" style="font-size: 2.5rem"
            >Create Account</span
          >
          <div class="small-spacer"></div>

          <b-form-group label="Username:" label-for="input-2">
            <b-form-input
              style="color: black !important"
              v-model="name"
              required
              type="text"
              placeholder="Enter Username"
            ></b-form-input>
          </b-form-group>

          <b-form-group
            label="Email address:"
            label-for="input-1"
            description="We'll never share your email with anyone else."
          >
            <b-form-input
              style="color: black !important"
              v-model="email"
              type="email"
              required
              placeholder="Enter email"
            ></b-form-input>
          </b-form-group>

          <b-form-group
            label="Password:"
            label-for="input-2"
            description="Password must not be less than 6 characters"
          >
            <b-form-input
              v-model="password"
              style="color: black !important"
              required
              type="password"
              placeholder="Enter Password"
            ></b-form-input>
          </b-form-group>

          <div class="small-spacer"></div>

          <b-button
            @click="onSignup"
            variant="primary"
            style="background: #ff8d1b; width: 100%; font-size: 18px; font-weight: 500"
            >Create an Account</b-button
          >
          <div class="small-spacer"></div>
          <span style="font-size: 14px"
            >Already have an Account? <span>Sign In</span></span
          >
        </b-form>
      </div>
      <div class="col-xl-4 col-lg-4 col-md-4"></div>
    </div>
  </div>
</template>

<script>
export default {
  middleware: "auth",
  auth: "guest",
  layout: "none",
  data() {
    return {
      email: "",
      name: "",
      password: ""
    };
  },
  methods: {
    async onSignup() {
      try {
        let data = {
          name: this.name,
          email: this.email,
          password: this.password
        };

        let requestToken = $axios.$get(
          `https://api.themoviedb.org/3/authentication/token/new?api_key=${process.env.api_key}`
        );
        let session = this.$axios.$post(
          `https://api.themoviedb.org/3/authentication/session/new?api_key=${process.env.api_key}`,
          data
        );
        const [respRequestToken, respSession] = await Promise.all([
          requestToken,
          session
        ]);
        // (`https://www.themoviedb.org/authenticate/${requestToken}`);
        console.log(requestToken.request_token);

        if (
          this.name !== "" &&
          this.email !== "" &&
          this.password !== "" &&
          respRequestToken.success
          // respSession.success
        ) {
          this.$auth.loginWith("local", {
            data: {
              email: this.email,
              password: this.password
            }
          });
          {
            window.location.replace(
              `https://www.themoviedb.org/authenticate/${requestToken.request_token}?redirect_to=http://localhost:3000`
            );
          }
          this.$router.push("/");
        }

        // if (response.success) {
        //   this.$auth.loginWith("local", {
        //     data: {
        //       email: this.email,
        //       password: this.password
        //     }
        //   });
        //   this.$router.push("/");
        // }
      } catch (error) {
        console.log(error);
      }
    }
  }
};
</script>
