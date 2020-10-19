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

        <!--  Menu Navigations -->
        <div>
  <b-nav class="menu-style">
    <b-nav-item active>HOME</b-nav-item>
    <b-nav-item>MOVIES</b-nav-item>
    <b-nav-item>TV-SERIES</b-nav-item>
    <b-nav-item>BY POPULARIY</b-nav-item>
    <b-nav-item>YOUR FAVOURITES</b-nav-item>
  </b-nav>
</div>
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
.menu-style{
  background: #FF8D1B;
  color: white;
  justify-content: center;
}

.navStyles{
}
</style>>
</style>
