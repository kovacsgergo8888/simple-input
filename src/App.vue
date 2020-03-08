<template>
  <div id="app">
    {{aValue}}<br>
    <reusable-input v-model="aValue"/>
  </div>
</template>

<script>
import ReusableInput from './components/ReusableInput'

export default {
  name: 'App',
  components: {
    ReusableInput
  },
  data () {
    return {
      aValue: ''
    }
  }
}
</script>

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
