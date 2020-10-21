<template>
  <main style="background: ">
    <div class="row">
      <div class="col-2"></div>
      <div class="col-10">
        <!-- Movie Display -->
        <span>Movies</span>
        <div class="force row">
          <div class="test" v-for="movie in movies" :key="movie.id">
            <b-card-group>
              <b-card
                :img-src= "`https://image.tmdb.org/t/p/w154/${movie.poster_path}`"
                text-variant="black"
              >
                <h5> {{movies.title}}</h5>
              </b-card>
            </b-card-group>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
export default {
  components: {},

  async asyncData({ $axios }) {
    try {
      let response = await $axios.$get(
        "https://api.themoviedb.org/3/movie/popular?api_key=e6a5ea6901b10430e9110114c0fa6799"
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
.small-spacer {
  width: 100%;
  margin-top: 1rem;
}
.large-spacer {
  width: 100%;
  margin-top: 3rem;
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
</style>
