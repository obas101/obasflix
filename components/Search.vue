<template>
  <div class="search">
    <input placeholder="Search for Movies" type="text" v-model="query"/>
    <button  @click="onSearch">GO</button>
  </div>
</template>
<script>
export default {
  data() {
    return {
      query: ""
    };
  },
  methods: {
    onSearch() {
      this.$router.push({
        path: "/search",
        query: { title: this.query }
      });
    }
  }
};
</script>
