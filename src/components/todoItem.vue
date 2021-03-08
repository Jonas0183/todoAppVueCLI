<template>
  <div>
    <input
      type="checkbox"
      :id="id"
      :checked="done"
      @input="$emit('change-input', { id, done: $event.target.checked })"
    />
    <label :for="id">{{ task }}</label>
  </div>
</template>
<script>
export default {
  props: {
    task: { required: true, type: String },
    done: { default: false, type: Boolean },
    id: { required: true, type: String },
  },
};
</script>
<style lang="scss">
</style>