<template>
  <div class="container">
    <div class="wrapper flex">
      <div class="font-input--min flex-col">
        <label for="font-min">MIN-FontSize</label>
        <input type="text" name="font-min" />
      </div>
      <div class="font-input--max flex-col">
        <label for="font-max">MAX-FontSize</label>
        <input type="text" name="font-max" />
      </div>
    </div>
    <div class="wrapper flex">
      <div class="width-input--min flex-col">
        <label for="width-min">MIN-ScreenWidth</label>
        <input type="text" name="width-min" />
      </div>
      <div class="width-input--max flex-col">
        <label for="width-max">MAX-ScreenWidth</label>
        <input type="text" name="width-max" />
      </div>
    </div>
  </div>
</template>
<script>
export default {};
</script>
<style lang="scss" scoped>
@use "../scss/setup/index" as *;

.container {
  width: 100%;

  display: flex;
  flex-direction: column;

  //justify-content: center;

  .wrapper:first-child {
    margin-bottom: 2rem;
  }

  .font-input,
  .width-input {
    &--max {
      margin-left: 2rem;
    }
  }

  .font-input {
    margin-bottom: 2rem;
  }

  label {
    margin-bottom: 0.25rem;
  }

  input {
    border: none;
    padding: 0.5rem;
    border-radius: 5px;
    box-shadow: 0 0 4px $clr-shadow inset;
  }
}
</style>
