<template>
  <div>
    <div class="container">
      <p>{{ resultString }}</p>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      resultString: `clamp(1.5rem, 5vw, 3rem)`,
    };
  },
};
</script>
<style lang="scss" scoped>
.container {
  font-family: "Roboto Mono", monospace;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
