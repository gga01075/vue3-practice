<template>
  <div>
    <button v-on:click="increment">Counter : {{ counter }}</button>
  </div>
</template>

<script>
import { onMounted, ref } from 'vue';

export default {
  setup() {
    // data
    const counter = ref(0);

    // method
    const increment = () => counter.value++;

    // mount
    onMounted(() => {
      console.log('컴포넌트가 마운트 되었습니다');
    });

    return {
      counter,
      increment,
    };
  },
};
</script>

<style lang="scss" scoped></style>
