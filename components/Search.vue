<template>
  <div>
    <input placeholder="Search for Movies/TV-Shows" v-model="query" />
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
  width: 15rem;
  padding-top: 5px;
  padding-bottom: 5px;
  border-radius: 30px;
  padding-left: 10px;
  border-color: #ff8d1b;
  outline: none;
}
input:hover {
  outline: none;
  border-color: white;
}
input:active {
  outline: none;
  border-color: white;
}
button {
  background: #ff8d1b;
  color: white;
  padding: 5px 8px 5px 8px;
  outline: none;
  text-align: center;
  border-radius: 20px;
  font-weight: 700;
}
button:active{
  outline: none;
}
</style>
