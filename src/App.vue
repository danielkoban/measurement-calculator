<template>
  <div id="app">
    <LanguageChanger/>
  </div>
</template>

<script>
import LanguageChanger from "./components/LanguageChanger.vue";

export default {
  name: "app",
  components: {
    LanguageChanger
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html {
  font-family: Arial, Helvetica, sans-serif;
}

body {
  background: #dbf1ff;
}
</style>
