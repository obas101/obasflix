<template>
  <div>
    <div class="row">
      <div class="col-xl-4 col-lg-4 col-md-4"></div>
      <div class="col-xl-4 col-lg-4 col-md-4">
        <b-form @submit="onSubmit" @reset="onReset" v-if="show">
          <span class="header-styles" style="font-size: 2.5rem"
            >Create a Free Account</span
          >
          <b-form-group
            id="input-group-1"
            label="Email address:"
            label-for="input-1"
            description="We'll never share your email with anyone else."
          >
            <b-form-input
              id="input-1"
              v-model="form.email"
              type="email"
              required
              placeholder="Enter email"
            ></b-form-input>
          </b-form-group>

          <b-form-group
            id="input-group-2"
            label="Username:"
            label-for="input-2"
          >
            <b-form-input
              id="input-2"
              v-model="form.name"
              required
              placeholder="Enter Username"
            ></b-form-input>
          </b-form-group>

          <b-form-group
            id="input-group-2"
            label="Password:"
            label-for="input-2"
          >
            <b-form-input
              id="input-2"
              v-model="form.password"
              required
              placeholder="Enter Password"
            ></b-form-input>
          </b-form-group>
          <div class="large-spacer"></div>
          <b-button
            type="submit"
            variant="primary"
            style="background: #ff8d1b; width: 100%; font-size: 18px; font-weight: 500"
            >Create an Account</b-button
          >
          <div class="small-spacer"></div>
          <span style="font-size: 14px">Already have an Account? <span>Sign In</span></span>
        </b-form>
      </div>
      <div class="col-xl-4 col-lg-4 col-md-4"></div>
    </div>
  </div>
</template>

<script>
export default {
  layout: "none",
  data() {
    return {
      form: {
        email: "",
        name: "",
        food: null,
        checked: []
      },
      foods: [
        { text: "Select One", value: null },
        "Carrots",
        "Beans",
        "Tomatoes",
        "Corn"
      ],
      show: true
    };
  },
  methods: {
    onSubmit(evt) {
      evt.preventDefault();
      alert(JSON.stringify(this.form));
    },
    onReset(evt) {
      evt.preventDefault();
      // Reset our form values
      this.form.email = "";
      this.form.name = "";
      this.form.food = null;
      this.form.checked = [];
      // Trick to reset/clear native browser form validation state
      this.show = false;
      this.$nextTick(() => {
        this.show = true;
      });
    }
  }
};
</script>
