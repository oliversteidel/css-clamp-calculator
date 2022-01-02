<template>
  <Header />
</template>

<script>
import Header from "./components/Header.vue";

export default {
  name: "App",
  components: {
    Header,
  },
};
</script>

<style lang="scss">
@use "./scss/setup/index" as *;

#app {
  font-family: "Roboto", sans-serif;
}
</style>
