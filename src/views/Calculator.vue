<template>
  <div>
    <EnMeasureButton v-bind:language="language"/>
  </div>
</template>

<script>
import EnMeasureButton from "../components/EnMeasureButton";

export default {
  name: "Calculator",
  components: {
    EnMeasureButton
  },
  props: ["language"]
};
</script>

<style>
</style>
