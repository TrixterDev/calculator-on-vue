<script setup lang="ts">
import { ref, reactive } from 'vue'
const first = ref<number>(0)
const second = ref<number>(0)
const apperations = reactive(['+', '-'])
const apper = ref<string>('+')
const result = ref<number>()

const compare = () => {
  switch (apper.value) {
    case '+':
      result.value = first.value + second.value
      break
    default:
      result.value = first.value - second.value
      break
  }
}
</script>

<template>
  <div>
    <h1>This is my calculator!</h1>
    <p>Enter your integer in input</p>
  </div>
  <div>
    <input v-model="first" type="number" />
    <select v-model="apper">
      <option v-for="apperation of apperations" v-bind:value="apperation" v-bind:key="apperation">
        {{ apperation }}
      </option>
    </select>
    <input v-model="second" type="number" />
    <button @click="compare">=</button>
  </div>
  <h3>{{ result }}</h3>
</template>
