<template>
  <header class="header">
    <h1 class="header__element--big">Measurement calculator</h1>
    <h2 class="header__element--small">Convert US and European measurement units</h2>
  </header>
</template>

<script>
export default {
  name: "Header"
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
