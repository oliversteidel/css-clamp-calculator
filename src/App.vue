<template>
  <div id="app">
    <Header />
    <Inputs />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Inputs from "./components/Inputs.vue";

export default {
  name: "App",
  components: {
    Header,
    Inputs,
  },
};
</script>

<style lang="scss">
@use "./scss/setup/index" as *;

#app {
  font-family: "Roboto", sans-serif;
  background: $clr-white;
}
</style>
