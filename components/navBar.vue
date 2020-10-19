<template>
  <main>
      <div>
        <b-navbar class="navStyles" toggleable="lg" type="dark" variant="dark">
          <b-navbar-brand href="#">OBASFLIX</b-navbar-brand>

          <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

          <b-collapse id="nav-collapse" is-nav>
            <!-- Right aligned nav items -->
            <b-navbar-nav class="ml-auto">
              <b-nav-form>
                <b-form-input
                  size="xl"
                  class="mr-sm-2"
                  placeholder="Search for your favourite Movies"
                ></b-form-input>
                <b-button size="xl" class="my-2 my-sm-0" type="submit"
                  >Search</b-button
                >
              </b-nav-form>
            </b-navbar-nav>
          </b-collapse>
        </b-navbar>
      </div>
  </main>
</template>

<script>
export default {};
</script>

<style scoped>
.mr-sm-2{
  width: 23rem;
  text-align: center;
  justify-content: center;
  justify-self: center;
}
.my-sm-0{

}
.navStyles{
}
</style>>
</style>
