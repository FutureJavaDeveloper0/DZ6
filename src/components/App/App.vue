<script setup>
import { Teleport,ref } from 'vue';
import Header from "../Header/Header.vue";
import css from "./App.module.css";
import Main from "../Main/Main.vue";

const isShow = ref(false);

</script>

<template>
  <div :class="css.page">
    <Header />
    <h1 :class="css.page_text">Your messages</h1>
    <Main />
  </div>
</template>

<style lang="scss" scoped>

</style>
