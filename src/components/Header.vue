<template>
  <div class="header">
    <div class="logo">
      <img src="../assets/logo.svg" alt="" />
    </div>
    <div class="title">
      <h1>css-clamp() Calculator</h1>
    </div>
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

  padding: 1rem 3rem;
  background: $clr-light-grey;
  box-shadow: $clr-shadow;

  .title {
    padding-left: 2rem;
  }
  h1 {
    font-weight: 400;
  }
}
</style>
