<template>
  <div>
    <div v-bind:key="item.id" class="measureButton" v-for="item in items">
      <div>
        <p>{{item.usMeasureSymbol}}</p>
        <p>{{item.usMeasureName}}</p>
      </div>
      <div>
        <p>{{item.euMeasureSymbol}}</p>
        <p>{{item.euMeasureName}}</p>
      </div>
    </div>
  </div>
</template>

<script>
import { measuresInEnglish } from "../data/measures.js";

export default {
  name: "MeasureButton",
  data() {
    return {
      items: measuresInEnglish
    };
  }
};
</script>

<style scoped>
.measureButton {
  cursor: pointer;
}

.measureButton:nth-of-type(1) {
  background: #ff4b47;
}

.measureButton:nth-of-type(2),
.measureButton:nth-of-type(3) {
  background: #ffbe25;
}

.measureButton:nth-of-type(4),
.measureButton:nth-of-type(5),
.measureButton:nth-of-type(6),
.measureButton:nth-of-type(7) {
  background: #27c787;
}

.measureButton:nth-of-type(8),
.measureButton:nth-of-type(9) {
  background: #70d7ff;
}
</style>
