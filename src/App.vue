<template>
  <DataBinding />
</template>

<script>
import DataBinding from "./components/DataBinding.vue";

export default {
  name: "App",
  components: {
    DataBinding,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  box-sizing: border-box;
}
body {
  margin: 0;
  background-color: #f589be;
}
</style>
