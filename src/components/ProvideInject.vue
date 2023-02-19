<template>
  <div class="container py-4">
    <div class="card">
      <div class="card-header">ProvideInject Component</div>
      <div class="card-body">
        <button @click="count++">add count</button>
        <p>appMessage : {{ appMessage }}</p>
        <Child></Child>
      </div>
      1
    </div>
  </div>
</template>

<script>
import { provide, ref, readonly, inject } from 'vue';
import Child from './Child.vue';
export default {
  components: {
    Child,
  },
  setup() {
    const staticMessagge = 'static message';
    const message = ref('message');
    const count = ref(10);

    const updateMessage = appendMessage => {
      message.value = message.value + appendMessage;
    };

    provide('static-message', staticMessagge);
    provide('message', { message: readonly(message), updateMessage });
    provide('count', count);

    const appMessage = inject('app-message');
    return { count, appMessage };
  },
};
</script>

<style lang="scss" scoped></style>
