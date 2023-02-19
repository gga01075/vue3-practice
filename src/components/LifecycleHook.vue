<template>
  <div class="container py-4">
    <input ref="inputRef" type="text" value="hello world" />
    <LifecycleChild v-if="visible"></LifecycleChild>
    <hr />
    <button @click="visible = !visible">Toggle Child</button>
    <p id="message">{{ message }}</p>
  </div>
</template>

<script>
import { ref, onBeforeMount, onMounted, onBeforeUpdate, onUpdated } from 'vue';
import LifecycleChild from './LifecycleChild.vue';

export default {
  components: { LifecycleChild },
  setup() {
    console.log('setup');
    const inputRef = ref(null);
    const message = ref('');
    const visible = ref(false);
    // onBeforeMount(() => {
    //   console.log('onBeforeMount');
    // });
    // onMounted(() => {
    //   console.log('onMount', inputRef.value.value);
    // });
    // onBeforeUpdate(() => {
    //   console.log('onBeforeUpdate', message.value);
    //   console.log(
    //     'DOM Content::',
    //     document.querySelector('#message').textContent,
    //   );
    // });
    // onUpdated(() => {
    //   console.log('onUpdated', message.value);
    //   console.log(
    //     'DOM Content::',
    //     document.querySelector('#message').textContent,
    //   );
    // });
    return { inputRef, message, visible };
  },
  beforeCreate() {
    console.log('beforeCreate');
  },
  created() {
    console.log('created');
  },
};
</script>

<style scoped></style>
