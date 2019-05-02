<template>
  <header class="header">
    <div v-if="!obj.show">
      <h1 class="header__element--big">Measurement calculator</h1>
      <h2 class="header__element--small">Convert US and European measurement units</h2>
    </div>
    <div v-else>
      <h1 class="header__element--big">Kalkulator miar</h1>
      <h2 class="header__element--small">Przelicz amerykańskie i europejskie jednostki</h2>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
  props: ["obj"]
};
</script>

<style scoped>
.header__element--big {
  font-size: 2rem;
  margin-top: 45px;
  margin-bottom: 40px;
}

.header__element--small {
  font-size: 1.25rem;
  margin-bottom: 65px;
}

.header__element--big,
.header__element--small {
  font-weight: normal;
}
</style>
