<template>
  <label class="child-class" style="border: 1px solid black" id="child-id">
    {{ label }}
    <input type="text" v-model="value" />
    <!-- :value="modelValue"
        @input="event => $emit('update:modelValue', event.target.value)" -->
  </label>
</template>

<script>
import { computed } from 'vue';

export default {
  props: ['modelValue', 'label'],
  emits: ['update:modelValue'],
  setup(props, { emit }) {
    const value = computed({
      get() {
        return props.modelValue;
      },
      set(value) {
        emit('update:modelValue', value);
      },
    });
    return { value };
  },
};
</script>

<style lang="scss" scoped></style>
