<template>
  <div class="header">
    <h1>Clamp Calculator</h1>
  </div>
</template>
<script>
export default {};
</script>
<style lang="scss" scoped>
@use "../scss/setup/index" as *;

.header {
  display: flex;
  align-items: center;
  width: 100vw;
  height: 5rem;
  padding: 1rem 3rem;
  background: $clr-light-grey;
  box-shadow: $clr-shadow;

  h1 {
    font-weight: 400;
  }
}
</style>
