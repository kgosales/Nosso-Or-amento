<template>
  <main>
    <div class="container">
      <FormValor @enviarValor="handleValor" />
      <h1>{{ valorCalculado }}</h1>
      <h2>{{ valorDizimo }}</h2>
    </div>
  </main>
</template>

<script setup>
import { ref } from 'vue'
import FormValor from '../components/FormValor.vue'

const valorCalculado = ref(0)
const valorDizimo = ref(0)

function handleValor(valorRecebido) {
  valorCalculado.value = valorRecebido[0]
  valorDizimo.value = valorRecebido[1]
}
</script>

<style lang="less" scoped>
main {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  flex-grow: 1;
}
</style>