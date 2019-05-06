<template>
  <div>
    <EnMeasureButton v-bind:language="language" v-if="!language.changed"/>
    <PlMeasureButton v-bind:language="language" v-else/>
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
