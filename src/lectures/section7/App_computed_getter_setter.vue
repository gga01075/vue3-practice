<template>
  <div>
    <h2>이름</h2>
    <p>{{ fullName }}</p>
  </div>
</template>

<script>
import { ref, computed } from 'vue';

export default {
  setup() {
    const firstName = ref('홍');
    const lastName = ref('길동');

    const fullName = computed({
      get() {
        return firstName.value + ' ' + lastName.value;
      },
      set(value) {
        [firstName.value, lastName.value] = value.split(' ');
      },
    });

    fullName.value = '짐 코딩';

    return { fullName };
  },
};
</script>
