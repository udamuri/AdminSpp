<template>
  <select
    class="border-gray-300 focus:border-indigo-300 focus:ring focus:ring-indigo-200 focus:ring-opacity-50 rounded-md shadow-sm"
    @change="$emit('update:modelValue', $event.target.value)"
    ref="select"
  >
    <option>{{selectLabel.value}}</option>
    <option
      v-for="(data, key) in options"
      :key="key"
      :value="data.id"
      :selected="data.id === modelValue"
    >
      {{ data.name }}
    </option>
  </select>
</template>

<script>
export default {
  props: ["modelValue", "options", "selectLabel"],

  emits: ["update:modelValue"],

  methods: {
    focus() {
      this.$refs.select.focus();
    },
  },
};
</script>
