<template>
  <div>
    <div class="row">
      <div class="col-xl-4 col-lg-4 col-md-4"></div>
      <div class="col-xl-4 col-lg-4 col-md-4">
        <div class="large-spacer"></div>
        <b-form style="padding: 1rem">
          <span class="header-styles" style="font-size: 2.5rem"
            >Login Account</span
          >
          <div class="small-spacer"></div>

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
            @click="onLogin"
            variant="primary"
            style="background: #ff8d1b; width: 100%; font-size: 18px; font-weight: 500"
            >Login</b-button
          >
          <div class="small-spacer"></div>
          <span style="font-size: 14px"
            >Dont have an Account?
            <span><nuxt-link to="/signup"> Sign Up</nuxt-link></span></span
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
      password: ""
    };
  },
  methods: {
    async onLoginup() {
      try {
        this.$auth.loginWith("local", {
          data: {
            email: this.email,
            password: this.password
          }
        });
        this.$router.push("/");
      } catch (error) {
        console.log(error);
      }
    }
  }
};
</script>
