<template>
  <main>
    <div class="container">
      <FormValor @enviarValor="handleValor" />
      <table>
        <tr>
          <td class="title">Investimento:</td>
          <td>R${{ resultado.investimento }}</td>
        </tr>
        <tr>
          <td class="title">Custo de Vida:</td>
          <td>R${{ resultado.custoVida }}</td>
        </tr>
        <tr>
          <td class="title">Estilo de Vida:</td>
          <td>R${{ resultado.estiloVida }}</td>
        </tr>
      </table>
    </div>
  </main>
</template>

<script setup>
import { ref } from 'vue'
import FormValor from '../components/FormValor.vue'

const resultado = ref({})
const valorDizimo = ref(0)

function handleValor(valorRecebido) {

  valorDizimo.value = valorRecebido[1]

  let orcamento = {
    valor: valorRecebido[0],
    dizimo: valorRecebido[1],
    investimento: porcento(valorRecebido[0], 0.15),
    custoVida: porcento(valorRecebido[0], 0.50),
    estiloVida: porcento(valorRecebido[0], 0.35),
  }

  resultado.value = orcamento
}

const porcento = (valor, porcentagem) => {
  return valor * porcentagem
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

  table {
    width: 100%;
    margin-top: 40px;

    .title {
      width: 50%;
      font-weight: bold;
      text-align: right;
    }

    td {
      font-size: 28px;
      padding: 0 2.5px;
    }
  }
}
</style>