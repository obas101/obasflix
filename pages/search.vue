<template>
  <main class="main">
    <div class="row">
      <div class="col-1"></div>
      <div class="col-10">
        <!-- Movie Display -->
        <span>Movies</span>
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
  watchQuery: ["title"],

  async asyncData({ $axios, query }) {
    try {
      let movies = await $axios.$get(
        `https://api.themoviedb.org/3/search/movie?api_key=e6a5ea6901b10430e9110114c0fa6799&query=${query.title}`
      );
      console.log(movies);
      return {
        movies: movies.results
      };
    } catch (error) {npm
      console.log(error);
    }
  }
};
</script>