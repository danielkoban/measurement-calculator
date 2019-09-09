<template>
  <transition name="fade">
    <div v-show="isOpen" class="modal__container">
      <div class="modal">
        <button @click="isOpen = false; firstValue=''; secondValue=''" class="modal__close">
          <i class="fas fa-times"></i>
        </button>
        <h3 class="modal__header">{{header}}</h3>
        <div class="modal__measures">
          <label class="modal__measure" for="firstMeasure">
            <span class="modal__measure--right modal__measure--bold">{{usMeasureSymbol}}</span>
            <input class="modal__input" type="number" id="firstMeasure" v-model="firstValue" />
            <span class="modal__measure--right">{{usMeasureName}}</span>
          </label>
          <label class="modal__measure" for="secondMeasure">
            <span class="modal__measure--right modal__measure--bold">{{euMeasureSymbol}}</span>
            <input class="modal__input" type="number" id="secondMeasure" v-model="secondValue" />
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
      euMeasureName: "",
      firstValue: "",
      secondValue: ""
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
  },
  methods: {
    closeModale() {
      this.isOpen = false;
      this.firstValue = "";
      this.secondValue = "";
    }
  },
  watch: {
    firstValue: function(val) {
      const id = this.id;
      switch (id) {
        case 1:
          //fahrenheit to celsius
          this.firstValue = val;
          this.secondValue = (val - 32) / 1.8;
          break;
        case 2:
          //pound to kilogram
          this.firstValue = val;
          this.secondValue = val * 0.45359237;
          break;
        case 3:
          //ounce to gram
          this.firstValue = val;
          this.secondValue = val * 28.3495231;
          break;
        case 4:
          //mile to kilometer
          this.firstValue = val;
          this.secondValue = val * 1.609344;
          break;
        case 5:
          //yard to meter
          this.firstValue = val;
          this.secondValue = val * 0.9144;
          break;
        case 6:
          //foot to centimeter
          this.firstValue = val;
          this.secondValue = val * 30.48;
          break;
        case 7:
          //inch to millimeter
          this.firstValue = val;
          this.secondValue = val * 25.4;
          break;
        case 8:
          //gallon to liter
          this.firstValue = val;
          this.secondValue = val * 3.785411784;
          break;
        case 9:
          //liquid pint to milliliter
          this.firstValue = val;
          this.secondValue = val * 473.2;
          break;
      }
    },
    secondValue: function(val) {
      const id = this.id;
      switch (id) {
        case 1:
          //celsius to fahrenheit
          this.firstValue = val * 1.8 + 32;
          this.secondValue = val;
          break;
        case 2:
          //kilogram to pound
          this.firstValue = val / 0.45359237;
          this.secondValue = val;
          break;
        case 3:
          //gram to ounce
          this.firstValue = val / 28.3495231;
          this.secondValue = val;
          break;
        case 4:
          //kilometer to mile
          this.firstValue = val / 1.609344;
          this.secondValue = val;
          break;
        case 5:
          //meter to yard
          this.firstValue = val / 0.9144;
          this.secondValue = val;
          break;
        case 6:
          //centimeter to foot
          this.firstValue = val / 30.48;
          this.secondValue = val;
          break;
        case 7:
          //millimeter to inch
          this.firstValue = val / 25.4;
          this.secondValue = val;
          break;
        case 8:
          //liter to gallon
          this.firstValue = val / 3.785411784;
          this.secondValue = val;
          break;
        case 9:
          //milliliter to liquid pint
          this.firstValue = val / 473.2;
          this.secondValue = val;
          break;
      }
    }
  }
};
</script>

<style>
.modal__container {
  position: fixed;
  top: 0;
  left: 0;
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

@media (max-width: 980px) and {
  .modal {
    height: 85%;
  }
}

@media (max-width: 738px) {
  .modal {
    width: 80%;
    height: 85%;
  }
}

@media (max-width: 480px) {
  .modal__measures {
    flex-direction: column;
    justify-content: space-around;
  }
}
</style>
