<template>
  <main>
    <div>
      <!-- Logo in NavBar -->
      <b-navbar class="navStyles" toggleable="lg" type="dark" variant="dark">
        <b-navbar-brand class="logo-font" href="http://obasflix.netlify.com"
          >OBASFLIX</b-navbar-brand
        >

        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>
          <!-- Right aligned nav items -->
          <b-navbar-nav class="ml-auto">
            <b-navbar-nav>
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
          <b-nav-item active><a href="">HOME</a></b-nav-item>
          <b-nav-item><a href="">MOVIES</a></b-nav-item>
          <b-nav-item><a href="">TV-SERIES</a></b-nav-item>
          <b-nav-item><a href="">BY POPULARITY</a></b-nav-item>
          <b-nav-item><a href="">FAVOURITES</a></b-nav-item>
        </b-nav>
      </div>
    </div>
  </main>
</template>

<script>
import Search from "~/components/Search";
export default {
  components: {
    Search
  }
};
</script>

<style>
.logo-font {
  font-family: Impact, Haettenschweiler, "Arial Bold";
  font-size: 3rem;
  color: #ff8d1b !important;
}
.search-style {
  text-align: center;
  margin-right: 10rem;
}

.menu-style {
  background: #ff8d1b;
  color: white;
  justify-content: center;
}
</style>
