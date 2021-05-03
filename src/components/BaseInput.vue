<template>
  <div class="flex items-baseline">
    <label v-if="label" :for="id" class="font-bold block mr-2">
      {{ label }}:
    </label>
    <input
      v-bind="$attrs"
      :value="modelValue"
      :placeholder="label"
      :type="type"
      @input="$emit('update:modelValue', $event.target.value)"
      class="block w-1/2 px-3 py-2 text-xl border border-gray-300 rounded-md shadow-sm focus:ring-primary-500 focus:border-primary-500 sm:text-sm focus:outline-none"
    />
  </div>
</template>

<script>
export default {
  name: 'BaseInput',
  props: {
    id: {
      type: String,
      default: '',
    },
    label: {
      type: String,
      default: '',
    },
    modelValue: {
      type: [String, Number],
      default: '',
    },
    type: {
      type: String,
      default: 'text',
    },
  },
}
</script>
