<template>
  <div>
    <h2>input Value</h2>
    <input type="text" v-model="inputValue" />
    <div>{{ inputValue }}</div>

    <h2>textarea value</h2>
    <textarea v-model="textareaValue"></textarea>
    <div>{{ textareaValue }}</div>

    <h2>checkbox value</h2>
    <label for="checkbox">{{ checkboxValue }}</label>
    <input id="checkbox" type="checkbox" v-model="checkboxValue" />

    <h2>radio value</h2>
    <label for="radio">
      <input type="radio" name="type" value="O" v-model="radioValue" />
      O형
    </label>
    <label for="radio">
      <input type="radio" name="type" value="A" v-model="radioValue" />
      A형
    </label>
    <div>{{ radioValue }}</div>

    <h2>select value</h2>
    <select v-model="selectValue">
      <option value="html">HTML 수업</option>
      <option value="css">CSS 수업</option>
      <option value="javascript">JavaScript 수업</option>
    </select>
    <div>{{ selectValue }}</div>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const inputValue = ref(null);
    const textareaValue = ref(null);
    const checkboxValue = ref(true);
    const radioValue = ref('O');
    const selectValue = ref('html');
    return {
      inputValue,
      textareaValue,
      checkboxValue,
      radioValue,
      selectValue,
    };
  },
};
</script>

<style lang="scss" scoped></style>
