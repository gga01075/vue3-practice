<template>
  <div>
    <form action="">
      <input type="text" v-model="title" placeholder="Title" />
      <textarea v-model="content" placeholder="Contents"></textarea>
    </form>
  </div>
</template>

<script>
import { ref, watchEffect } from 'vue';

export default {
  setup() {
    const title = ref('');
    const contents = ref('');

    watchEffect(() => {
      console.log(title.value);
      console.log(contents.value);
    });

    return { title, contents };
  },
};
</script>

<style lang="scss" scoped></style>
