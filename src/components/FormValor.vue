<template>
    <form @submit.prevent>
        <label for="valor">Valor</label>
        <input type="text" name="valor" id="valor" v-model="valor" placeholder="R$ 0,00">
        <div class="checkbox-box">
            <input type="checkbox" name="dizimo" id="dizimo" value="dizimo" v-model="dizimo">
            <label for="dizimo">Dízimo</label>
        </div>
        <button @click="enviarValor">Calcular</button>
    </form>
</template>

<script setup>
import { ref, defineEmits } from 'vue'

const valor = ref()
const dizimo = ref()

const emit = defineEmits(['enviarValor'])

function enviarValor() {
    emit('enviarValor', [valor.value, dizimo.value])
}
</script>

<style lang="less" scoped>
form {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;

    label {
        width: 100%;
        text-align: left;
        font-weight: bold;
        font-size: larger;
    }

    input[type="text"] {
        width: 100%;
        padding: 10px;
        border: none;
        border-bottom: 3px solid var(--secondary-color);
        margin-bottom: 20px;
        font-size: 42px;

        &:focus {
            outline: none;
        }
    }

    .checkbox-box {
        display: flex;
        align-items: center;
        margin-bottom: 20px;

        input {
            margin-right: 10px;
        }
    }

    button {
        width: 70%;
        padding: 10px;
        border: none;
        border-radius: 25px;
        background-color: var(--secondary-color);
        color: white;
        font-weight: bold;
        cursor: pointer;
        transition: all 0.3s;

        &:hover {
            background-color: var(--primary-color);
        }
    }
}
</style>