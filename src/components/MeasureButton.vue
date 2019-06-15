<template>
  <div class="buttonWrapper">
    <div v-bind:key="item.id" class="measureButton" v-for="item in items">
      <div>
        <p class="measureButton__symbol--bold">{{item.usMeasureSymbol}}</p>
        <p>{{item.usMeasureName}}</p>
      </div>
      <i class="fas fa-arrows-alt-h measureButton__icon"></i>
      <div>
        <p class="measureButton__symbol--bold measureButton__symbol--right">{{item.euMeasureSymbol}}</p>
        <p>{{item.euMeasureName}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "MeasureButton",
  props: ["items"]
};
</script>

<style>
.buttonWrapper {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-gap: 30px;
}

.measureButton {
  position: relative;
  display: flex;
  justify-content: space-between;
  padding: 8px 10px;
  align-items: center;
  border-radius: 5px;
  cursor: pointer;
  transition: all 0.4s;
}

.measureButton:nth-of-type(1) {
  background: #ff4b47;
}

.measureButton:nth-of-type(2),
.measureButton:nth-of-type(3) {
  background: #ffbe25;
}

.measureButton:nth-of-type(4),
.measureButton:nth-of-type(5),
.measureButton:nth-of-type(6),
.measureButton:nth-of-type(7) {
  background: #27c787;
}

.measureButton:nth-of-type(8),
.measureButton:nth-of-type(9) {
  background: #70d7ff;
}

.measureButton:hover {
  /*filter: saturate(125%);*/
  /*animation: move 1s ease;*/
  padding: 0 30px;
}

.measureButton__symbol--bold {
  margin-bottom: 8px;
  font-weight: bold;
}

.measureButton__symbol--right {
  text-align: right;
}

.measureButton__icon {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 1.5rem;
}

@keyframes move {
  0 % {
    transform: translate(-50%, -50%);
  }
  33.33% {
    transform: translate(-150%, -50%);
  }
  66.66% {
    transform: translate(100%, -50%);
  }
  100% {
    transform: translate(-50%, -50%);
  }
}
</style>
