<template>
  <div>
    <slot>
      <h1>Header</h1>
    </slot>
  </div>
</template>

<script>
export default {
  name: "appHead",
  data: () => ({}),
};
</script>

<style lang="scss">
h1 {
  font-size: 5vw;
  color: #270681;
  background-color: #dad1f5;
}
</style>