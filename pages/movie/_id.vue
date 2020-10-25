<template>
  <main>
    <div class="main-body-2"></div>
    <div class="large-spacing"></div>
    <div class="row">
      <div class="col-xl-2 col-lg-2 col-md-2 col-2"></div>
      <div class="col-xl-3 col-lg-3 col-md-3 col-3">
        <img
          :src="`https://image.tmdb.org/t/p/w300/${movie.poster_path}`"
          alt=""
        />
      </div>
      <div class="col-xl-5 col-lg-5 col-md-5 col-5">
        <div>
          <span class="movie-title">{{ movie.title }}</span>
          <br />
          <hr />
          <!-- Watchlist-->
          <div><button>Add to Watchlist</button></div>

          <!-- Description-->
          <div>
            <span class="movie-description">{{ movie.overview }}</span>
          </div>
          <div class="small-spacing"></div>

          <!-- Movie Genres-->
          <div>
            <span>{{ movie.genres.name }}</span>
          </div>
          <div class="small-spacing"></div>

          <!-- movie info -->
          <div>
            <div>{{ movie.parentalGuide }}</div>
            <div>{{ movie.release_date }}</div>
            <div>{{ movie.runtime }}mins</div>
            <div>{{ movie.vote_average }}/ 10</div>
          </div>
          <div class="large-spacing"></div>

          <!-- production companies -->
          <div class="row">
            <div>Company Name</div>
            <div>{{ movie.production_companies.name }}</div>
          </div>

          <!-- production country -->
          <div class="row">
            <div>Production Country</div>
            <div>{{ movie.production_companies.origin_country }}</div>
          </div>

          <!-- status -->
          <div class="row">
            <div>cast</div>
            <div>{{ movie.status }}</div>
          </div>

          <!-- language -->
          <div>
            <div>cast</div>
            <div>{{ movie.spoken_languages.name }}</div>
          </div>
        </div>
      </div>
      <div class="col-xl-2 col-lg-2 col-md-2 col-2"></div>
    </div>

    <!-- Similar Movies Section -->
    <div><h1>Similar Movies</h1></div>
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
<style>
body {
  font-family: sans-serif !important;
}
.main-body-2 {
  margin-top: 12rem;
}
.movie-title {
  font-weight: 400;
  line-height: 46px;
  font-size: 35px;
}
.movie-description {
  font-weight: 400;
  font-size: 14px;
  line-height: 18px;
}
</style>
