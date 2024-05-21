<template>
  <div>
    <HeaderGeral />
    <RouterView />
    <FooterGeral />
  </div>
</template>

<script setup>
import { RouterView } from 'vue-router'
import HeaderGeral from './components/HeaderGeral.vue'
import FooterGeral from './components/FooterGeral.vue'
</script>

<style lang="less" scoped>
div {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>