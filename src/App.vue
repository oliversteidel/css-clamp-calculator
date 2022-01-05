<template>
  <div id="app">
    <Header />
    <main>
      <section class="top">
        <Inputs v-on:show-string="setResult($event)" />
        <Preview />
      </section>
      <section class="bottom">
        <Result :resultString="resultString" />
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
  data() {
    return {
      resultString: null,
    };
  },
  methods: {
    setResult(str) {
      this.resultString = "";
      this.resultString = str;
    },
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
