<template>
  <div></div>
</template>

<script>
import { ref, reactive } from 'vue';
export default {
  setup() {
    // ref -> Object
    const countData = ref(0);
    const state = reactive({
      count: countData,
    });

    console.log(countData.value);
    console.log('state.count : ', state.count);

    // ref => Array
    const message = ref('Hello');
    const arr = reactive([message]);
    console.log('arr[0] : ', arr[0].value);

    return {};
  },
};
</script>

<style lang="scss" scoped></style>
