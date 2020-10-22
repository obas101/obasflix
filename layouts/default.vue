<template>
  <div>
    <navBar />
    <div class="main-body">
      <Nuxt />
    </div>
  </div>
</template>

<script>
import navBar from "~/components/navBar";
export default {
  components: { navBar }
};
</script>

<style>
.main-body {
  margin-top: 7.5rem;
}
.header-styles{
  font-size: 20px;
  color: #ff8d1b;
  font-weight: 600;
}
.small-spacer {
  width: 100%;
  margin-top: 1rem;
}
.large-spacer {
  width: 100%;
  margin-top: 3rem;
}
</style>
