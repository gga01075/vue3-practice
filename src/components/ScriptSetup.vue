<template>
  <div class="container py-4">
    {{ msg }}
    <button @click="sayHello">clciik</button>
    <input v-model="message" type="text" />
    <PostItem type="news" title="제목" contents="내용" isLike="true"></PostItem>

    <hr />
    <MyButton class="parent-class"></MyButton>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import axios from 'axios';
import PostItem from '@/components/setup/PostItem.vue';
import MyButton from '@/components/setup/MyButton.vue';

const msg = 'Hello World';
const message = ref('');
const sayHello = () => {
  alert('Hello world');
};

const response = await axios(
  'https://dummy.restapiexample.com/api/v1/employees',
);
console.log('response::', response);
</script>

<style scoped></style>
