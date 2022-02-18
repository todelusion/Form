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
}
</style>
