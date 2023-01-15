<template>
  <div>
    <!-- 배열 반복해서 출력-->
    <ul>
      <li v-for="(item, index) in items" :key="item.id">
        인덱스: {{ index }}, {{ item.message }}
      </li>
    </ul>

    <!-- id가 짝수인 것만 노출하고싶다면 (template태그사용) -->
    <ul>
      <template v-for="(item, index) in items" :key="item.id">
        <li v-if="item.id % 2 === 0">
          ID: {{ item.id }} 인덱스 : {{ index }}, {{ item.message }}
        </li>
      </template>
    </ul>

    <!-- id가 짝수인 것만 노출하고싶다면 (computed 사용) -->
    <ul>
      <li v-for="(item, index) in evenItems" :key="item.id">
        ID: {{ item.id }} 인덱스 : {{ index }}, {{ item.message }}
      </li>
    </ul>

    <hr />

    <!-- 객체 반복해서 출력-->
    <ul>
      <li v-for="(value, key, index) in myObject" :key="key">
        {{ index }} - {{ key }} - {{ value }}
      </li>
    </ul>
  </div>
</template>

<script>
import { reactive, computed } from 'vue';
export default {
  setup() {
    const items = reactive([
      { id: 1, message: 'Java' },
      { id: 2, message: 'HTML' },
      { id: 3, message: 'CSS' },
      { id: 4, message: 'JavaScript' },
    ]);

    const myObject = reactive({
      title: '제목',
      author: '홍길동',
      publisheAt: '2023-01-15',
    });

    const evenItems = computed(() => items.filter(item => item.id % 2 === 0));
    return {
      items,
      myObject,
      evenItems,
    };
  },
};
</script>

<style lang="scss" scoped></style>
