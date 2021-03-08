<template>
  <button @click="cleanDone">Limpiar</button>
</template>
<script>
export default {
  methods: {
    cleanDone() {
      this.$emit("clean");
    },
  },
};
</script>
<style lang="scss">
</style>