<template>
  <div class="p-3 bg-danger">
    <button class="btn btn-primary" type="button" @click="sayHello">
      My Button
    </button>
  </div>
</template>

<script>
export default {
  setup(props, context) {
    // console.log('context.attrs::', context.attrs);
    // console.log('context.attrs.class::', context.attrs.class);
    // console.log('context.attrs.id::', context.attrs.id);
    // console.log('context.attrs.onClick::', context.attrs.onClick);

    const sayHello = () => {
      context.emit('sayHello');
    };
    return { sayHello };
  },
};
</script>

<style lang="scss" scoped></style>
