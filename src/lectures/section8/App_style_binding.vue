<template>
  <div>
    <div :style="styleObject">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptates,
      laudantium mollitia! Et delectus excepturi vero laudantium, sunt fuga
      optio, vel laboriosam, fugit obcaecati quaerat eius ipsam. Libero esse
      facilis eaque!
    </div>
    <button v-on:click="fontSize--">-</button>
    <button v-on:click="fontSize++">+</button>
  </div>
</template>

<script>
import { ref, computed } from 'vue';
export default {
  setup() {
    // const styleObject = reactive({
    //   color: 'red',
    //   fontSize: '13px',
    // });
    const fontSize = ref(13);
    const styleObject = computed(() => {
      return {
        color: 'red',
        fontSize: fontSize.value + 'px',
      };
    });

    return { fontSize, styleObject };
  },
};
</script>

<style lang="scss" scoped></style>
