<template>
  <div v-show="isOpen" class="modal">
    <button @click="isOpen = false" class="modal__close">
      <i class="fas fa-times"></i>
    </button>
    <h3>Convert units</h3>
    <div>
      <label for>
        {{usMeasureSymbol}}
        <input type="text">
        {{usMeasureName}}
      </label>
      <label for>
        {{euMeasureSymbol}}
        <input type="text">
        {{euMeasureName}}
      </label>
    </div>
  </div>
</template>

<script>
export default {
  name: "Modal",
  data() {
    return {
      isOpen: false,
      id: null,
      usMeasureSymbol: "",
      usMeasureName: "",
      euMeasureSymbol: "",
      euMeasureName: ""
    };
  },
  mounted() {
    this.$root.$on(
      "clicked",
      (id, usMeasureSymbol, usMeasureName, euMeasureSymbol, euMeasureName) => {
        console.log(id);
        this.id = id;
        this.usMeasureSymbol = usMeasureSymbol;
        this.usMeasureName = usMeasureName;
        this.euMeasureSymbol = euMeasureSymbol;
        this.euMeasureName = euMeasureName;
        this.isOpen = true;
      }
    );
  }
};
</script>

<style>
.modal {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 50%;
  height: 50%;
  background: #ffffff;
  border-radius: 5px;
}

.modal__close {
  position: absolute;
  top: 0;
  right: 0;
  transform: translate(50%, -50%);
  width: 35px;
  height: 35px;
  border-radius: 50%;
  border: none;
  outline: none;
  font-size: 1.2rem;
  text-align: center;
  line-height: 35px;
  cursor: pointer;
}
</style>
