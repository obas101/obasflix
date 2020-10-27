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
        <div class="small-spacer"></div>
        <div>
          <span class="movie-title">{{ movie.title }}</span>
          <br />
          <div class="small-spacer"></div>

          <span class="tagline">{{ movie.tagline }}</span>
          <div class="small-spacer"></div>
          <div>
            <hr class="line" />
          </div>
          <!-- Favorite-->
          <div><button>Add to WatchList</button></div>
          <div class="large-spacer"></div>

          <!-- Description-->
          <div>
            <span class="movie-description">{{ movie.overview }}</span>
          </div>
          <div class="small-spacer"></div>

          <!-- Movie Genres-->
          <div>
            <div
              class="production_details"
              v-for="genre in movie.genres"
              :key="genre.id"
            >
              <span>{{ genre.name }}&nbsp;&nbsp;</span>
            </div>
          </div>
          <div class="small-spacer"></div>

          <!-- movie info -->
          <div class="movie-info">
            <div>Release Date: {{ movie.release_date }}</div>
            <div>Run Time: {{ movie.runtime }}mins</div>
            <div>Rating: {{ movie.vote_average }}/10</div>
          </div>
          <div class="large-spacer"></div>
          <div class="production-info">
            <!-- production company -->
            <div>
              <span class="sub-heading">Production Companies: </span>
              <div
                class="production_details"
                v-for="production in movie.production_companies"
                :key="production.id"
              >
                <div>{{ production.name }},&nbsp;</div>
              </div>
            </div>
            <div class="small-spacer"></div>

            <!-- production countries -->
            <div class="">
              <span class="sub-heading">Production Countries: </span>
              <div
                class="production_details"
                v-for="country in movie.production_countries"
                :key="country.id"
              >
                <div>{{ country.name }},&nbsp;</div>
              </div>
            </div>
            <div class="small-spacer"></div>
            <!-- status -->
            <div class="">
              <div>
                <span class="sub-heading">Status:</span>
                <span class="production_details">{{ movie.status }}</span>
              </div>
            </div>
            <div class="small-spacer"></div>
            <!-- language -->
            <div>
              <span class="sub-heading">Spoken Languages:</span>
              <div
                class="production_details"
                v-for="language in movie.spoken_languages"
                :key="language.id"
              >
                <div>{{ language.name }},&nbsp;</div>
              </div>
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
      console.log(movies);
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
.tagline {
  font-weight: 400;
  font-size: 12px;
  letter-spacing: 0.3px;
  color: #ff8d1b;
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
  font-size: 13px;
}
.production-info {
  line-height: 1.5rem !important;
}
.line {
  border-color: white;
}
.production_details {
  display: inline-block !important;
  font-size: 13px;
  color: #ff8d1b;
}
</style>
