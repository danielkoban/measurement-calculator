<template>
  <transition name="fade">
    <div v-show="isOpen" class="modal__container">
      <div class="modal">
        <button @click="isOpen = false" class="modal__close">
          <i class="fas fa-times"></i>
        </button>
        <h3 class="modal__header">{{header}}</h3>
        <div class="modal__measures">
          <label class="modal__measure" for="firstMeasure">
            <span class="modal__measure--right modal__measure--bold">{{usMeasureSymbol}}</span>
            <input class="modal__input" type="number" id="firstMeasure" />
            <span class="modal__measure--right">{{usMeasureName}}</span>
          </label>
          <label class="modal__measure" for="secondMeasure">
            <span class="modal__measure--right modal__measure--bold">{{euMeasureSymbol}}</span>
            <input class="modal__input" type="number" id="secondMeasure" />
            <span class="modal__measure--right">{{euMeasureName}}</span>
          </label>
        </div>
      </div>
    </div>
  </transition>
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
  props: ["header"],
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
.modal__container {
  position: absolute;
  top: 0;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  background: #dbf1ff;
}

.modal {
  width: 680px;
  height: 380px;
  padding: 50px;
  background: #ffffff;
  border-radius: 5px;
  position: relative;
  /*box-shadow: 0 10px 20px rgba(0, 0, 0, 0.19), 0 6px 6px rgba(0, 0, 0, 0.23);*/
  border-bottom: #c8dbe8 3px solid;
}

.modal__header {
  font-weight: normal;
}

.modal__measures {
  height: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.modal__measure {
  display: flex;
  flex-direction: column;
}

.modal__measure--right {
  text-align: right;
}

.modal__measure--bold {
  font-weight: bold;
  margin-bottom: 8px;
}

.modal__input {
  margin-bottom: 8px;
  padding: 5px;
  border: none;
  border-bottom: #dddddd 2px solid;
  outline: none;
  font-size: 1rem;
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

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>
