<template>
  <div id="app">
    <LanguageChanger/>
    <Header/>
    <Calculator/>
  </div>
</template>

<script>
import LanguageChanger from "./components/LanguageChanger.vue";
import Header from "./components/Header";
import Calculator from "./views/Calculator";

export default {
  name: "app",
  components: {
    LanguageChanger,
    Header,
    Calculator
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
  font-family: "Roboto", sans-serif;
  color: #212529;
}

body {
  background: #dbf1ff;
}
</style>
