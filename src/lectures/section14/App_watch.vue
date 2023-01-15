<template>
  <div>123</div>
</template>

<script>
import { ref, watch } from 'vue';

export default {
  setup() {
    const message = ref('');

    watch(message, (newValue, oldValue) => {
      // DOM 조작할때
      // API를 호출해서 또다른 반응형 상태를 변경할 때
      console.log(`newValue : ${newValue}`);
      console.log(`oldValue : ${oldValue}`);
    });

    return { message };
  },
};
</script>

<style lang="scss" scoped></style>
