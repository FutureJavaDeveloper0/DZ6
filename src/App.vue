<script setup>
import { Teleport,ref } from 'vue';
import Modal from "./components/Modal/Modal.vue";

const isShow = ref(false);

</script>

<template>
  <button @click="isShow = !isShow">Show</button>
  <Modal :show="isShow" @close="isShow = false"> Hello! This is my site on vue.js! 1111111111111111111111111</Modal>

</template>

<style lang="scss" scoped>

</style>
