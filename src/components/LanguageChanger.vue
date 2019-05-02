<template>
  <aside class="language-changer">
    <p class="language-changer__value">English</p>
    <label class="language-changer__switch">
      <input class="language-changer__input" type="checkbox" v-model="language.changed" value="1">
      <span class="language-changer__slider--round"></span>
    </label>
    <p class="language-changer__value">Polski</p>
  </aside>
</template>

<script>
export default {
  name: "LanguageChanger",
  props: ["language"]
};
</script>

<style scoped>
.language-changer {
  display: flex;
  align-items: center;
  justify-content: flex-end;
  padding-top: 10px;
}
.language-changer .language-changer__value {
  margin: 0 5px;
}
.language-changer .language-changer__switch {
  position: relative;
  display: inline-block;
  width: 60px;
  height: 34px;
  margin: 0;
}
.language-changer .language-changer__switch .language-changer__input {
  display: none;
}
.language-changer .language-changer__switch .language-changer__slider--round {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #ccc;
  border-radius: 34px;
  -webkit-transition: 0.4s;
  transition: 0.4s;
}
.language-changer
  .language-changer__switch
  .language-changer__slider--round:before {
  position: absolute;
  content: "";
  height: 26px;
  width: 26px;
  left: 4px;
  bottom: 4px;
  background-color: white;
  border-radius: 50%;
  -webkit-transition: 0.4s;
  transition: 0.4s;
}

.language-changer__input:checked + .language-changer__slider--round {
  background-color: #2196f3;
}

.language-changer__input:focus + .language-changer__slider--round {
  box-shadow: 0 0 1px #2196f3;
}

.language-changer__input:checked + .language-changer__slider--round:before {
  -webkit-transform: translateX(26px);
  -ms-transform: translateX(26px);
  transform: translateX(26px);
}
</style>
