<template>
  <div>
    <h1>{{ header }}</h1>
  </div>
</template>

<script>
export default {
  name: "appHead",
  data: () => ({
    header: "To-Do list App",
  }),
};
</script>

<style lang="scss">
h1 {
  font-size: 5vw;
  color: #270681;
  background-color: #dad1f5;
}
</style>