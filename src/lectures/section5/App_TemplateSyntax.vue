<template>
  <div>
    <h2>보간법</h2>
    <p>문자열 : {{ message }}</p>

    <h2>보간법(v-once 사용)</h2>
    <p v-once>문자열 : {{ message }}</p>
    <button @click="message = message + '!'">Click!</button>

    <hr />
    <h2>HTML(v-html)</h2>
    <p v-html="rawHtml"></p>

    <hr />
    <h2>속성 바인딩</h2>
    <div v-bind:title="dynamicTitle">마우스를 올려보세요</div>
    <input type="text" value="홍길동" v-bind:disabled="isInputDisabled" />
    <input v-bind="attrs" />
  </div>
</template>

<script>
import { ref } from 'vue';
export default {
  setup() {
    const message = ref('안녕하세요!');
    const rawHtml = ref('<strong>안녕하세요</strong>');
    const dynamicTitle = ref('안녕하세요!!!');
    const isInputDisabled = ref(true);
    const attrs = ref({
      type: 'password',
      value: '123456',
      disabled: false,
    });
    return {
      message,
      rawHtml,
      dynamicTitle,
      isInputDisabled,
      attrs,
    };
  },
};
</script>

<style lang="scss" scoped></style>
