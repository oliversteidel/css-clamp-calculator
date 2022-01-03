<template>
  <div id="app">
    <Header />
    <main>
      <section class="top">
        <Inputs />
        <Preview />
      </section>
      <section class="bottom">
        <Result />
      </section>
    </main>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Inputs from "./components/Inputs.vue";
import Preview from "./components/Preview.vue";
import Result from "./components/Result.vue";

export default {
  name: "App",
  components: {
    Header,
    Inputs,
    Preview,
    Result,
  },
};
</script>

<style lang="scss">
@use "./scss/setup/index" as *;

#app {
  font-family: "Roboto", sans-serif;
  color: $clr-black;

  main {
    min-height: 100vh;
    padding-top: 10rem;
    background: $clr-white;

    .top {
      display: flex;
      align-items: flex-end;
      padding: 2rem 4rem;
    }
  }
}
</style>
