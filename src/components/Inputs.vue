<template>
  <div class="container">
    <div class="wrapper flex">
      <div class="font-input--min flex-col">
        <label for="font-min">MIN-FontSize</label>
        <input type="text" name="font-min" v-model="fontMin" />
      </div>
      <div class="font-input--max flex-col">
        <label for="font-max">MAX-FontSize</label>
        <input type="text" name="font-max" v-model="fontMax" />
      </div>
    </div>
    <div class="wrapper flex">
      <div class="width-input--min flex-col">
        <label for="width-min">MIN-ScreenWidth</label>
        <input type="text" name="width-min" v-model="widthMin" />
      </div>
      <div class="width-input--max flex-col">
        <label for="width-max">MAX-ScreenWidth</label>
        <input type="text" name="width-max" v-model="widthMax" />
      </div>
    </div>
    <button @click="$emit(calculate, resultString)">Calculate</button>
  </div>
</template>
<script>
export default {
  data() {
    return {
      fontMin: null,
      fontMax: null,
      widthMin: null,
      widthMax: null,
    };
  },
  computed: {
    slope() {
      return (this.fontMax - this.fontMin) / (this.widthMax - this.widthMin);
    },
    yAxisIntersection() {
      return -this.widthMin * slope + this.fontMin;
    },
    resultString() {
      return `${this.fontMin}, ${this.yAxisIntersection}rem + ${
        this.slope * 100
      }vw, ${this.fontMax}`;
    },
  },
};
</script>
<style lang="scss" scoped>
@use "../scss/setup/index" as *;

.container {
  width: 100%;
  display: flex;
  flex-direction: column;

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

  button {
    display: block;
    width: 13.0625rem;
    margin-top: 2rem;
    padding: 0.5rem;
    border: none;
    background: $clr-light-grey;
    border-radius: 5px;
    box-shadow: 3px 3px 5px $clr-shadow;
    cursor: pointer;
  }
}
</style>
