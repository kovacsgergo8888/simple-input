<script setup>
import { ref, reactive } from 'vue'

const props = defineProps(['modelValue'])
const emit = defineEmits(['update:modelValue'])
let input = ref(null)
const state = reactive({
  localValue: props.modelValue
})

const onUpdate = () => {
  emit('update:modelValue', state.localValue)
  input.value.blur()
}

const cancel = () => {
  state.localValue = props.modelValue
  input.value.blur()
}
</script>

<template>
  <input
    v-model="state.localValue"
    ref="input"
    @keydown.enter="onUpdate"
    @blur="onUpdate"
    @keydown.esc="cancel"
    @click="$refs.input.select()"
    type="text"
  />
</template>
