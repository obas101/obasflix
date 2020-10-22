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
.title-style {
  font-size: 1rem !important;
  padding: none;
  text-align: center;
  justify-content: center;
  width: 100%;
}
.header-styles {
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
.center-spacer{
  width: 2rem;
}
</style>
