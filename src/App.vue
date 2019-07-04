<template>
  <div id="app" class="app__container">
    <LanguageChanger v-bind:language="language" />
    <Header v-bind:language="language" />
    <Calculator v-bind:language="language" />
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
  },
  data() {
    return {
      language: {
        changed: false
      }
    };
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

.app__container {
  max-width: 1440px;
  min-height: 100vh;
  margin: 0 auto;
  padding: 0 30px;
}

@media (max-width: 738px) {
  .app__container {
    padding: 0 10px;
  }
}
</style>
