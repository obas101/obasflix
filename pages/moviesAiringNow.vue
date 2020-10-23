<template>
  <main class="main">
    <div class="row">
      <div class="col-1"></div>
      <div class="col-10">
        <div class="large-spacer"></div>
        <!-- Movie Display -->

        <span class="header-styles">Movies Airing Now</span>
        <div class="small-spacer"></div>
        <div class="force row">
          <div class="test" v-for="movie in movies" :key="movie.id">
            <b-card
              class="card-style title-style"
              :img-src="`https://image.tmdb.org/t/p/w185/${movie.poster_path}`"
              text-variant="white"
              :title="movie.title"
              style="max-width: 190px"
            >
              <div style="width: 100%"></div>
              <!-- <span class="title-style">{{ movie.title }}</span> -->
            </b-card>
          </div>
        </div>
      </div>
      <div class="col-1"></div>
    </div>
  </main>
</template>

<script>
export default {
  components: {},

  async asyncData({ $axios }) {
    try {
      let response = await $axios.$get(
        `https://api.themoviedb.org/3/movie/now_playing?api_key=${process.env.api_key}`
      );
      return {
        movies: response.results
      };
    } catch (error) {
      console.log(error);
    }
  }
};
</script>

<style>
.main {
  background: black;
}
.card-style {
  background: black !important;
}
.force {
  justify-content: center;
}
.test {
  padding: 1rem;
}
h6 {
  font-size: 10px;
}
.title-style {
  font-size: 1rem !important;
  padding: none;
  text-align: center;
  justify-content: center;
  width: 100%;
}
.card-title {
  font-size: 15px;
}
</style>
