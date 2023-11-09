<template>
    <div>
        <p>Counte: {{ count }}</p>
        <button @click="increment5">+5</button>
        <button @click="increment">+</button>
        <button @click="decrement">-</button>
        <button @click="decrement5">-5</button>

        <input type="number" v-model="inputValue" placeholder="Enter a number" />
        <button @click="incrementCustom">+ Custom</button>
        <button @click="decrementCustom">- Custom</button>
        <button @click="reset">reset</button>
        <p>{{ message }}</p>
    </div>
</template>

<script>
//変更を監視するためにrefをインポート
import { ref } from 'vue'

export default {
    name: 'CounterComponents',
    setup() {
        const count = ref(0)
        const inputValue = ref(0)
        const message = ref('')
        const increment = () => {
            count.value++
            if (count.value > 10) {
                count.value = 10
                message.value = '10以上はカウントできません'
            }
            // messageを戻す
            if (count.value < 10) {
                message.value = ''
            }
        }
        const increment5 = () => {
            count.value += 5
            if (count.value > 10) {
                count.value = 10
                message.value = '10以上はカウントできません'
            }
            // messageを戻す
            if (count.value < 10) {
                message.value = ''
            }
        }
        const incrementCustom = () => {
            count.value += Number(inputValue.value)
            if (count.value > 10) {
                count.value = 10
                message.value = '10以上はカウントできません'
            }
            // messageを戻す
            if (count.value < 10) {
                message.value = ''
            }
        }
        const decrement = () => {
            count.value--
            if (count.value < 0) {
                count.value = 0
                message.value = '0未満はカウントできません'
            }
            // messageを戻す
            if (count.value > 0) {
                message.value = ''
            }
        }
        const decrement5 = () => {
            count.value -= 5
            if (count.value < 0) {
                count.value = 0
                message.value = '0未満はカウントできません'
            }
            // messageを戻す
            if (count.value > 0) {
                message.value = ''
            }
        }
        const decrementCustom = () => {
            count.value -= Number(inputValue.value)
            if (count.value < 0) {
                count.value = 0
                message.value = '0未満はカウントできません'
            }
            // messageを戻す
            if (count.value > 0) {
                message.value = ''
            }
        }
        const reset = () => {
            count.value = 0
            message.value = ''
        }
        return {
            count,
            increment,
            increment5,
            incrementCustom,
            decrement,
            decrement5,
            decrementCustom,
            reset,
            message,
            inputValue
        }
    }
}
</script>

<style scoped>
p {
    font-size: 2em;
    color: #42b983;
}

button {
    font-size: 1em;
    margin-right: 10px;
    padding: 5px 10px;
    border-radius: 5px;
    border: 1px solid #42b983;
    color: #42b983;
    background: #fff;
    cursor: pointer;
}
</style>