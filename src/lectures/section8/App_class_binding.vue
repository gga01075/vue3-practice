<template>
  <div>
    <div :class="classObject">텍스트 입니다.</div>
    <button v-on:click="toggle">toggle</button>
    <button v-on:click="hasError = !hasError">toggle Error</button>
  </div>
</template>

<script>
import { ref, computed } from 'vue';
export default {
  setup() {
    const isActive = ref(true);
    const hasError = ref(false);

    // const classObject = reactive({
    //   active: true,
    //   'text-danger': true,
    // });

    const classObject = computed(() => {
      return {
        active: true,
        'text-danger': true,
      };
    });

    const toggle = () => {
      isActive.value = !isActive.value;
    };

    return { isActive, toggle, hasError, classObject };
  },
};
</script>

<style scoped>
.active {
  font-weight: 900;
}

.text-danger {
  color: red;
}
</style>
