<script setup>
import axios from 'axios';
import { onMounted, ref } from "vue";

const msg = ref("你好，前端工程化");

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

<template>
 <h1>{{ msg }}</h1> 
</template>

<style lang="scss">
body {
  background-color: skyblue;
  h1{
    align-items: center;
  }
}
</style>
