<template>
  <select :value="modelValue" @change="cangeOption">
    <option disabled value="">Выберите из списка</option>
    <option 
      v-for="option in options"
      :key="option.value"
      :value="option.value"
    >
      {{ option.name }}
    </option>
  </select>
  
</template>

<script>
export default {
  name: 'my-select',
  props: {
    modelValue: {
      type: String
    },
    options: {
      type: Array,
      default: () => []
    }
  },
  methods: {
    cangeOption(event) {
      this.$emit('update:modelValue', event.target.value)
    }
  }
}
</script>

<style>

</style>