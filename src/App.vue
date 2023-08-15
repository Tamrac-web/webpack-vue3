<script setup>
import axios from 'axios';
import { onMounted, ref } from "vue";

const msg = ref("你好世界！Hello World!");

const getData = () => {
  axios.get('/api/test').then(response => {
    msg.value = response.data.data.msg;
  }).catch(error => {
    console.error(error);
  });
};

onMounted(() => {
  getData();
});
</script>

<!-- test修改 -->
<template>
 <h1>{{ msg }}</h1> 
</template>

<style lang="scss">
body {
  background-color: skyblue;
  h1{
    text-align: center;
  }
}
</style>
