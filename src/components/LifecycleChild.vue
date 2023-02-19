<template>
  <div class="card">
    <div class="card-body">Lifecycle Child</div>
  </div>
</template>

<script>
import {
  ref,
  onBeforeMount,
  onMounted,
  onBeforeUnmount,
  onUnmounted,
} from 'vue';

export default {
  setup() {
    // console.log('[Child] setup');
    onBeforeMount(() => {
      console.log('[Child] onBeforeMount');
    });
    onMounted(() => {
      console.log('[Child] onMount');
    });
    onBeforeUnmount(() => {
      console.log('[Child] onBeforeUnmount');
    });
    onUnmounted(() => {
      console.log('[Child] onUnmount');
    });
    return {};
  },
};
</script>

<style lang="scss" scoped></style>
