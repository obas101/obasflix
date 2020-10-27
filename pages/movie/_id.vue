<template>
  <main>
    <div class="main-body-2"></div>
    <div class="large-spacing"></div>
    <div class="row">
      <div class="col-xl-2 col-lg-2 col-md-2"></div>
      <div class="col-xl-3 col-lg-3 col-md-3">
        <img
          :src="`https://image.tmdb.org/t/p/w300/${movie.poster_path}`"
          alt=""
        />
      </div>
      <div class="col-xl-5 col-lg-5 col-md-5">
        <div>
          <span class="movie-title">{{ movie.title }}</span>
          <div class="small-spacer"></div>
          <div>
            <hr class="line" />
          </div>
          <!-- Watchlist-->
          <div><button>Add to Watchlist</button></div>
          <div class="large-spacer"></div>

          <!-- Description-->
          <div>
            <span class="movie-description">{{ movie.overview }}</span>
          </div>
          <div class="small-spacer"></div>

          <!-- Movie Genres-->
          <div>
            <span>{{ movie.genres.name }}</span>
          </div>
          <div class="small-spacer"></div>

          <!-- movie info -->
          <div class="movie-info">
            <div>{{ movie.parentalGuide }}</div>
            <div>Release Date: {{ movie.release_date }}</div>
            <div>Run Time: {{ movie.runtime }}mins</div>
            <div>Rating: {{ movie.vote_average }}/10</div>
          </div>
          <div class="large-spacer"></div>
          <div class="production-info">
            <!-- production companies -->
            <div class="">
              <div class="sub-heading">Company Name</div>
              <div>{{ movie.production_companies.name }}</div>
            </div>

            <!-- production country -->
            <div class="">
              <div class="sub-heading">Production Country</div>
              <div>{{ movie.production_companies.origin_country }}</div>
            </div>

            <!-- status -->
            <div class="">
              <div><span  class="sub-heading">Status:</span> {{ movie.status }}</div>
            </div>

            <!-- language -->
            <div>
              <div class="sub-heading">Language</div>
              <div>{{ movie.spoken_languages.name }}</div>
            </div>
          </div>
        </div>
      </div>
      <div class="col-xl-2 col-lg-2 col-md-2 col-2"></div>
    </div>

    <!-- Similar Movies Section -->
    <div class="large-spacer"></div>
    <div class="large-spacer"></div>
    <div><h1 class="header-styles">Similar Movies</h1></div>
    <hr />
  </main>
</template>

<script>
export default {
  async asyncData({ $axios, params }) {
    try {
      let movies = await $axios.$get(
        `https://api.themoviedb.org/3/movie/${params.id}?api_key=${process.env.api_key}`
      );
      return {
        movie: movies
      };
    } catch (error) {
      console.log;
    }
  }
};
</script>
<style scoped>
body {
  font-family: sans-serif !important;
}
.main-body-2 {
  margin-top: 12rem;
}
h1 {
  text-align: center !important;
}
.movie-title {
  font-weight: 400;
  line-height: 46px;
  font-size: 35px;
  letter-spacing: 1px;
}
.movie-description {
  font-weight: 200;
  font-size: 15px;
  line-height: 18px;
  letter-spacing: 0.5px;
}
.movie-info {
  font-weight: 300;
  font-size: 12px;
  line-height: 18px;
  letter-spacing: 1px;
}
.sub-heading {
  font-weight: 600;
  font-size: 15px;
}
.production-info {
  line-height: 1.5rem !important;
}
.line {
  border-color: white;
}
</style>
