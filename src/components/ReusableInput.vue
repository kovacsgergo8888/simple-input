<template>
  <input v-model="localValue"
         ref="input"
         @keydown.enter="emit"
         @blur="emit"
         @keydown.esc="cancel"
         @click="$refs.input.select()"
         type="text"/>
</template>

<script>
export default {
  name: 'ReusableInput',
  props: ['value'],
  data () {
    return {
      localValue: this.value
    }
  },
  methods: {
    emit () {
      this.$emit('input', this.localValue)
      this.$refs.input.blur()
    },
    cancel () {
      this.localValue = this.value
      this.$refs.input.blur()
    }
  }
}
</script>
