<template>
  <div>
    <EnMeasureButton v-if="!language.changed"/>
    <PlMeasureButton v-else/>
  </div>
</template>

<script>
import EnMeasureButton from "../components/EnMeasureButton";
import PlMeasureButton from "../components/PlMeasureButton";

export default {
  name: "Calculator",
  components: {
    EnMeasureButton,
    PlMeasureButton
  },
  props: ["language"]
};
</script>

<style>
</style>
