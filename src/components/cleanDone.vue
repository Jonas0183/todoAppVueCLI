<template>
  <div>
    <button @click="cleanDone">Limpiar</button>
  </div>
</template>
<script>
import bus from "../bus";
export default {
  methods: {
    cleanDone() {
      this.$emit("clean");
    },
  },
  computed: {
    percentToClean() {
      const n = bus.$on("to-clean", n);
      const total = bus.$on("total", total);
      console.log(n);
      return (total - n) / total;
    },
  },
};
</script>
<style lang="scss">
</style>