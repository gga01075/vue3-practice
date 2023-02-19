<template>
  <div class="container py-4">
    <input ref="input" type="text" />
    <p>{{ input }}</p>
    <p v-if="input">
      {{ input.value }},{{ $refs.input.value }}, {{ $refs.input === input }}
    </p>

    <hr />

    <ul>
      <li v-for="fruit in fruits" :key="fruit" ref="itemRef">{{ fruit }}</li>
    </ul>
  </div>
</template>

<script>
import { onMounted, ref } from 'vue';

export default {
  setup() {
    const input = ref(null);
    console.log('setup:', input.value);
    onMounted(() => {
      input.value.value = 'hello world';
      console.log('onMounted:', input.value);
      itemRef.value.forEach(item => {
        console.log('item:', item.textContent);
      });
    });

    const fruits = ref(['사과', '딸기', '포도']);
    const itemRef = ref([]);
    return { input, fruits, itemRef };
  },
};
</script>

<style lang="scss" scoped></style>
