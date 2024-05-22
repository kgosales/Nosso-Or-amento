<template>
    <form @submit.prevent>
        <label for="valor">Valor</label>
        <div id="valor-box">
            <div id="valor-input">
                <input type="number" name="valor" id="valor" v-model="valor" placeholder="R$ 0,00">
                <span id="drop" v-if="!drop" @click="drop = true">+</span>
                <span id="drop" v-if="drop" @click="drop = false">-</span>
            </div>
            <div v-if="drop">
                <div class="checkbox-box">
                    <input type="checkbox" name="dizimo" id="dizimo" value="dizimo" v-model="dizimo">
                    <label for="dizimo">Dízimo</label>
                </div>
            </div>
        </div>
        <button @click="enviarValor">Calcular</button>
    </form>
</template>

<script setup>
import { ref, defineEmits } from 'vue'

const valor = ref()
const dizimo = ref()

const drop = ref(false)

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
    row-gap: 20px;

    label {
        width: 100%;
        text-align: left;
        font-weight: bold;
        font-size: larger;
    }

    #valor-box {
        width: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        row-gap: 20px;
        position: relative;

        #valor-input {
            width: 100%;
            display: flex;
            align-items: center;
            justify-content: center;

            #valor {
                width: 100%;
                padding: 10px;
                border: none;
                border-bottom: 3px solid var(--secondary-color);
                font-size: 42px;

                &:focus {
                    outline: none;
                }

                &::-webkit-inner-spin-button,
                &::-webkit-outer-spin-button {
                    -webkit-appearance: none;
                    margin: 0;
                }
            }

            #drop {
                position: absolute;
                right: 10px;
                color: var(--secondary-color);
                font-size: 42px;
                font-weight: bold;
                cursor: pointer;

                &:hover {
                    color: var(--primary-color);
                }
            }
        }
    }

    .checkbox-box {
        display: flex;
        align-items: center;

        input {
            margin-right: 10px;
        }
    }

    button {
        width: 80%;
        max-width: 400px;
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