<template>
  <div class="container">
    <p class="preview-letter">A</p>
  </div>
</template>
<script>
export default {};
</script>
<style lang="scss" scoped>
@use "../scss/setup/index" as *;

.container {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;

  padding: 3rem;
  border-radius: 5px;
  background: #fff;
  box-shadow: 0 0 3px $clr-shadow inset;
}
</style>
