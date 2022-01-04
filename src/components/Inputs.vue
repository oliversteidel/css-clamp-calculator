<template>
  <div class="container">
    <div class="wrapper flex">
      <div class="font-input--min flex-col">
        <label for="font-min">MIN-FontSize</label>
        <div class="input-wrapper">
          <input type="text" name="font-min" v-model="inputFontMin" />
          <select name="unit" id="font-min-unit">
            <option value="px">px</option>
            <option value="rem">rem</option>
          </select>
        </div>
      </div>
      <div class="font-input--max flex-col">
        <label for="font-max">MAX-FontSize</label>
        <div class="input-wrapper">
          <input type="text" name="font-max" v-model="inputFontMax" />
          <select name="unit" id="font-max-unit">
            <option value="px">px</option>
            <option value="rem">rem</option>
          </select>
        </div>
      </div>
    </div>
    <div class="wrapper flex">
      <div class="width-input--min flex-col">
        <label for="width-min">MIN-ScreenWidth</label>
        <div class="input-wrapper">
          <input type="text" name="width-min" v-model="inputWidthMin" />
          <select name="unit" id="width-min-unit">
            <option value="px">px</option>
            <option value="rem">rem</option>
          </select>
        </div>
      </div>
      <div class="width-input--max flex-col">
        <label for="width-max">MAX-ScreenWidth</label>
        <div class="input-wrapper">
          <input type="text" name="width-max" v-model="inputWidthMax" />
          <select name="unit" id="width-max-unit">
            <option value="px">px</option>
            <option value="rem">rem</option>
          </select>
        </div>
      </div>
    </div>
    <button @click="sendData">Calculate</button>
  </div>
</template>
<script>
export default {
  data() {
    return {
      inputFontMin: null,
      inputFontMax: null,
      inputWidthMin: null,
      inputWidthMax: null,
    };
  },
  computed: {
    fontMin() {
      let number = parseFloat(this.inputFontMin);
      let unit = document.getElementById("font-min-unit").value;
      if (unit === "px") {
        number = number / 16;
      }
      return number;
    },
    fontMax() {
      let number = parseFloat(this.inputFontMax);
      let unit = document.getElementById("font-max-unit").value;
      if (unit === "px") {
        number = number / 16;
      }
      return number;
    },
    widthMin() {
      let number = parseFloat(this.inputWidthMin);
      let unit = document.getElementById("width-min-unit").value;
      if (unit === "px") {
        number = number / 16;
      }
      return number;
    },
    widthMax() {
      let number = parseFloat(this.inputWidthMax);
      let unit = document.getElementById("width-max-unit").value;
      if (unit === "px") {
        number = number / 16;
      }
      return number;
    },
    slope() {
      return (
        Math.round(
          ((this.fontMax - this.fontMin) / (this.widthMax - this.widthMin)) *
            10000
        ) / 10000
      );
    },
    yAxisIntersection() {
      return (
        Math.round((-this.widthMin * this.slope + this.fontMin) * 10000) / 10000
      );
    },
    resultString() {
      return `${this.fontMin}rem, ${this.yAxisIntersection}rem + ${
        this.slope * 100
      }vw, ${this.fontMax}rem`;
    },
  },
  methods: {
    sendData() {
      this.$emit("show-string", this.resultString);
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

  .input-wrapper {
    display: flex;
  }

  input {
    padding: 0.5rem;
    border: none;
    border-radius: 5px;
    box-shadow: 0 0 4px $clr-shadow inset;
  }

  select {
    min-height: 2.5rem;
    margin-left: 0.5rem;
    padding: 0.5rem;
    border: none;
    border-radius: 5px;
    box-shadow: 0 0 4px $clr-shadow inset;
    background: #fff;
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
