<script setup>
import ReusableInput from './components/ReusableInput.vue'
import {reactive} from 'vue'

const state = reactive({
  aValue: 'starting value'
})
</script>

<template>
  <div id="app">
    {{state.aValue}}<br>
    <reusable-input v-model="state.aValue"/>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
