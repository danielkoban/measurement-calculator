<template>
  <div class="buttonWrapper">
    <div v-bind:key="item.id" class="measureButton" v-for="item in items">
      <div>
        <p class="measureButton__symbol--bold">{{item.usMeasureSymbol}}</p>
        <p>{{item.usMeasureName}}</p>
      </div>
      <i class="fas fa-arrows-alt-h measureButton__icon"></i>
      <div>
        <p class="measureButton__symbol--bold measureButton__symbol--right">{{item.euMeasureSymbol}}</p>
        <p>{{item.euMeasureName}}</p>
      </div>
    </div>
  </div>
</template>

<script>
import { measuresInPolish } from "../data/measures.js";

export default {
  name: "MeasureButton",
  data() {
    return {
      items: measuresInPolish
    };
  }
};
</script>

<style>
</style>
