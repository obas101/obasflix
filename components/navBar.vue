<template>
  <main>
    <div class="main-nav">
      <!-- Logo in NavBar -->
      <b-navbar class="navStyles" toggleable="lg" type="dark" variant="dark">
        <b-navbar-brand class="logo-font" href="http://obasflix.netlify.com"
          >OBASFLIX</b-navbar-brand
        >

        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>
          <!-- Right aligned nav items -->
          <b-navbar-nav class="ml-auto">
            <!-- <span class="header-styles"
              ><nuxt-link class="link-style1" to="/"
                >Favourites</nuxt-link
              ></span
            > -->
            <div class="center-spacer"></div>
            <span class="header-styles"
              ><nuxt-link class="link-style1" to="/watchlist"
                >WatchList</nuxt-link
              ></span
            >
            <div class="center-spacer"></div>

            <span class="header-styles"
              ><nuxt-link class="link-style2" to="/signup">SignUp</nuxt-link>
              /<nuxt-link class="link-style2" to="/login"
                >Login</nuxt-link
              ></span
            >
            <div class="center-spacer"></div>

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
          <b-dropdown dropup class="m-2" offset-lg10 text="MOVIES">
            <b-dropdown-item>
              <NuxtLink @click="onPopularMovies" to="/popularMovies"
                >By Popularity</NuxtLink
              ></b-dropdown-item
            >
            <b-dropdown-item
              ><NuxtLink @click="moviesAiringNow" to="/moviesAiringNow"
                >Currently Airing</NuxtLink
              ></b-dropdown-item
            >
          </b-dropdown>
          <b-dropdown dropup class="m-2" text="TV-SERIES">
            <b-dropdown-item
              ><NuxtLink @click="onPopularTV" to="/popularTVShows"
                >By Popularity</NuxtLink
              ></b-dropdown-item
            >
            <b-dropdown-item
              ><NuxtLink @click="seriesAiringNow" to="/seriesAiringNow"
                >Currently Airing</NuxtLink
              ></b-dropdown-item
            >
          </b-dropdown>
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
  },
  methods: {
    onPopularMovies() {
      this.$router.push({
        path: "/popularMovies"
      });
    },
    moviesAiringNow() {
      this.$router.push({
        path: "/moviesAiringNow"
      });
    },
    onPopularTV() {
      this.$router.push({
        path: "/popularTVShows"
      });
    },
    seriesAiringNow() {
      this.$router.push({
        path: "/seriesAiringNow"
      });
    }
  }
};
</script>

<style>
.link-style1:hover {
  color: white;
  text-decoration: none;
}
.link-style1 {
  color: #ff8d1b;
  text-decoration: none;
  font-size: 16px;
}
.link-style2 {
  color: #ff8d1b;
  text-decoration: none;
  font-size: 14px;
}
.logo-font {
  font-family: sans-serif;
  font-size: 2.5rem;
  color: #ff8d1b !important;
  font-weight: 500;
}
.search-style {
  text-align: center;
  /* margin-right: 10rem; */
}

.menu-style {
  background: #ff8d1b;
  color: white;
  justify-content: center;
}
.navStyles {
  background: black !important;
  color: #ff8d1b !important;
}
.main-nav {
  overflow: hidden;
  z-index: 1;
  position: fixed;
  top: 0;
  width: 100%;
}
</style>
