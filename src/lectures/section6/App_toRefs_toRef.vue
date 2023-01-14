<template>
  <div>
    <p>author : {{ author }}</p>
    <p>title : {{ title }}</p>
  </div>
</template>

<script>
import { reactive, toRefs, toRef } from 'vue';

export default {
  setup() {
    const book = reactive({
      author: 'Vue Team',
      year: '2020',
      title: 'Vue3 Guide',
      description: '당신은 지금 바로 이 책을 읽습니다.',
      price: '무료',
    });

    const { author, title } = toRefs(book);
    const year = toRef(book, 'year');
    const price = toRef(book, 'price');

    return { author, title, book, year, price };
  },
};
</script>

<style lang="scss" scoped></style>
