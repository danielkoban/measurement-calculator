<template>
  <div>
    <MeasureButtons v-bind:items="$data[!language.changed ? 'enItems' : 'euItems']" />
    <Modal v-bind:header="!language.changed ? 'Convert units' : 'Przelicz jednostki'" />
  </div>
</template>

<script>
import MeasureButtons from "../components/MeasureButtons";
import Modal from "../components/Modal";
import { measuresInEnglish } from "../data/measures";
import { measuresInPolish } from "../data/measures";

export default {
  name: "Calculator",
  components: {
    MeasureButtons,
    Modal
  },
  data() {
    return {
      enItems: measuresInEnglish,
      euItems: measuresInPolish
    };
  },
  props: ["language"]
};
</script>

<style>
</style>
