<template>
  <main>
      <div>
        <b-navbar class="navStyles" toggleable="lg" type="dark" variant="dark">
          <b-navbar-brand href="#">OBASFLIX</b-navbar-brand>

          <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

          <b-collapse id="nav-collapse" is-nav>
            <!-- Right aligned nav items -->
                  <b-navbar-nav class="ml-auto">

            <b-navbar-nav >
                <div class="search-style">
                <Search />
                </div>
            </b-navbar-nav>
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
import Search from "~/components/Search"
export default {
  components: {
    Search
  }
};
</script>

<style scoped>
.search-style{
  text-align: center;
  margin-right: 10rem;
}

.menu-style{
  background: #FF8D1B;
  color: white;
  justify-content: center;
}

</style>>
</style>
