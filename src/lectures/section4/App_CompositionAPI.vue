<template>
  <div>
    <h2>반응형 메시지</h2>
    <p>{{ reactiveMessage }}</p>
    <button v-on:click="addReactiveMessage">Add Message</button>
    <h2>일반 메시지</h2>
    <p>{{ normalMessage }}</p>
    <button v-on:click="addNormalMessage">Add Message</button>
  </div>
</template>

<script>
import { ref, isRef, onMounted, onBeforeMount } from 'vue';
export default {
  setup() {
    console.log('setup');

    // 반응형 API(ref)
    const reactiveMessage = ref('Hello Reactive Message');
    const addReactiveMessage = () => {
      reactiveMessage.value = reactiveMessage.value + '!';
    };

    console.log(`isRef(reactiveMessage)`, isRef(reactiveMessage));

    // 일반 문자열
    let normalMessage = 'Hello Normal Message';
    const addNormalMessage = () => {
      normalMessage = normalMessage + '!';
    };

    // isRef는 해당 변수가 반응형 데이터인지 확인함
    console.log(`isRef(normalMessage)`, isRef(normalMessage));

    onMounted(() => {
      console.log('onMounted');
    });

    onBeforeMount(() => {
      console.log('onBeforeMount');
    });

    return {
      reactiveMessage,
      normalMessage,
      addReactiveMessage,
      addNormalMessage,
    };
  },
};
</script>

<style lang="scss" scoped></style>
