<template>
  <main>
    <div class="container py-4">
      <MyButton
        class="my-button"
        id="my-button"
        @say-hello="sayHello"
      ></MyButton>

      <hr />

      <FancyButton v-slot="{ fancyMessage }"> {{ fancyMessage }} </FancyButton>

      <FancyButton></FancyButton>

      <hr />
      <AppCard>
        <!-- <template #[slotArgs]>제목입니다.</template> -->
        <!-- <template #default>컨텐츠입니다.</template> -->
        <!-- 암시적으로 default 슬롯입니다
        <template #footer>footer입니다</template> -->
        <template #header="{ headerMessage }">
          {{ headerMessage }}
        </template>

        <template #default="slotProps">
          <!-- {{ slotProps }} -->
          디폴트입니다.
          <br />
          {{ slotProps.childMessage }}
          <br />
          {{ slotProps.helloMessage }}
        </template>

        <template #footer="{ footerMessage }">
          {{ footerMessage }}
        </template>
      </AppCard>

      <AppCard>
        <template #default="slotProps">
          <!-- {{ slotProps }} -->
          디폴트입니다.
          <br />
          {{ slotProps.childMessage }}
          <br />
          {{ slotProps.helloMessage }}
        </template>
      </AppCard>
    </div>
  </main>
</template>

<script>
import MyButton from '@/components/MyButton.vue';
import FancyButton from '@/components/FancyButton.vue';
import AppCard from '@/components/AppCard.vue';
import { ref } from 'vue';

export default {
  components: {
    MyButton,
    FancyButton,
    AppCard,
  },
  setup() {
    const sayHello = () => {
      alert('안녕하세요');
    };

    const slotArgs = ref('header');

    return { sayHello, slotArgs };
  },
};
</script>

<style lang="scss" scoped></style>
