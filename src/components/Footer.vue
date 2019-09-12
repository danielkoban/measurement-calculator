<template>
  <div class="information">
    <a href="https://github.com/danielkoban" rel="noopener noreferrer" target="_blank">
      <i class="fab fa-github"></i>
    </a>
  </div>
</template>

<script>
export default {
  name: "Footer"
};
</script>

<style>
.information {
  padding: 30px;
  display: flex;
  justify-content: center;
}

.fab {
  font-size: 2rem;
  color: #cccccc;
  transition: all 0.4s;
}

.fab:hover {
  color: #24292e;
  cursor: pointer;
}
</style>