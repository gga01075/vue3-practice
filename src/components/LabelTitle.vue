<template>
  <div>
    <label>
      {{ label }}
      <input type="text" v-model="value" />
    </label>
  </div>
</template>

<script>
import { computed } from 'vue';

export default {
  props: ['title', 'label'],
  emits: ['update:title'],
  setup(props, { emit }) {
    const value = computed({
      get() {
        return props.title;
      },
      set(value) {
        emit('update:title', value);
      },
    });
    return { value };
  },
};
</script>

<style lang="scss" scoped></style>
