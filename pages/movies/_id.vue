<template>
  <main>
    <div class="main-body-2"></div>
    <div class="large-spacing"></div>
    <div class="row">
      <div class="col-xl-6 col-lg-6 col-md-6 col-6">
        <div><img src="" alt="" /></div>
      </div>
      <div class="col-xl-6 col-lg-6 col-md-6 col-6">
        <div>
          <!-- <h1>{{ movies.name }}</h1> -->
          <br />
          <h5>{{ movies.original_title }}</h5>
          <br />
          <hr />
          <!-- Watchlist-->
          <div><button>Add to Watchlist</button></div>

          <!-- Description-->
          <div>
            <span>{{ movies.overview }}</span>
          </div>
          <div class="small-spacing"></div>

          <!-- Movie Genres-->
          <div>
            <!-- <span>{{ movies.genres.name }}</span> -->
          </div>
          <div class="small-spacing"></div>

          <!-- movie info -->
          <div>
            <div>{{ parentalGuide }}</div>
            <div>{{ movies.release_date }}</div>
            <div>{{ movies.runtime }}mins</div>
            <div>{{ movies.vote_average }}/ 10</div>
          </div>
          <div class="large-spacing"></div>

          <!-- production companies -->
          <div class="row">
            <!-- <div>Company Name</div> -->
            <!-- <div>{{ movies.production_companies.name }}</div> -->
          </div>

          <!-- production country -->
          <div class="row">
            <div>Production Country</div>
            <div>{{ movies.production_companies.origin_country }}</div>
          </div>

          <!-- status -->
          <div class="row">
            <div>cast</div>
            <div>{{ movies.status }}</div>
          </div>

          <!-- language -->
          <div>
            <div>cast</div>
            <!-- <div>{{ movies.spoken_languages.name }}</div> -->
          </div>
        </div>
      </div>
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
        movies: movies
      };
    } catch (error) {
      console.log;
    }
  }
};
</script>
<style>
.main-body-2 {
  margin-top: 10rem;
}
</style>
