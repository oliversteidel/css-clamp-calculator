<template>
  <div>
    <div class="container">
      <div class="wrapper">
        <p v-if="resultString != null">{{ resultString }}</p>
        <button :class="{ shadow: !isClicked }" @click="copyToClipboard">
          <img src="../assets/copy-thin.svg" alt="" />
        </button>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ["resultString"],
  data() {
    return {
      isClicked: false,
    };
  },
  methods: {
    copyToClipboard() {
      this.isClicked = true;
      navigator.clipboard.writeText(this.resultString);
      setTimeout(() => {
        this.isClicked = false;
      }, 50);
    },
  },
};
</script>
<style lang="scss" scoped>
@use "../scss/setup/index" as *;
.container {
  font-family: "Roboto Mono", monospace;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 4rem;

  .wrapper {
    position: relative;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 6rem;
    border-radius: 5px;
    background: #fff;
    box-shadow: 0 0 5px $clr-shadow inset;
    p {
      font-size: 2rem;
    }

    button {
      position: absolute;
      top: 1rem;
      right: 1rem;
      padding: 0.5rem;
      border: none;
      background: $clr-light-grey;
      border-radius: 5px;

      transition: all 0.2s ease-out;
    }

    button:hover {
      background: $clr-hover;
    }

    .shadow {
      box-shadow: 3px 3px 5px $clr-shadow;
    }
  }
}
</style>
