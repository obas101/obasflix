<template>
  <div>
    <div class="main-body">
      <Nuxt />
    </div>
  </div>
</template>

<script>
export default {
};
</script>

<style>
*body{
  margin: 0;
  padding: 0;
}
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
.title-style:hover {
  color: #ff8d1b;
  outline: none;
  text-decoration: none;
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
.center-spacer {
  width: 2rem;
}
body {
  background: black;
  color: white;
}

.aa.b-card:hover {
  outline: none;
  text-decoration: none;
  background: red;
  color: yellow;
}
</style>
