<template>
  <div>
    <input
      placeholder="Search for Movies and TV-Shows"
      type="text"
      v-model="query"
    />
    <button @click="onSearch">Search</button>
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
<style>
input {
  background: black;
  color: white !important;
  width: 18rem;
  padding-top: 5px;
  padding-bottom: 5px;
  border-radius: 30px;
  text-align: center;
  border-color: #ff8d1b;
}
button {
  background: #ff8d1b;
  color: white;
  padding: 5px;

  text-align: center;
  border-radius: 12px;
  font-weight: 700;
}
</style>
