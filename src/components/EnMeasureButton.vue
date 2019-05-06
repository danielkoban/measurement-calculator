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

<style>
</style>
