<template>
  <div>
    <div v-memo="[subscriber]">
      <p>subscriber : {{ subscriber }}</p>
      <p>views : {{ views }}</p>
      <p>likes : {{ likes }}</p>
    </div>
    <button @click="subscriber++">Subs++</button>
    <button @click="views++">Views++</button>
    <button @click="likes++">Likes++</button>

    <div>
      <p>subscriber : {{ subscriber }}</p>
      <p>views : {{ views }}</p>
      <p>likes : {{ likes }}</p>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue';
export default {
  setup() {
    const subscriber = ref(4000);
    const views = ref(400);
    const likes = ref(20);
    return { subscriber, views, likes };
  },
};
</script>

<style lang="scss" scoped></style>
