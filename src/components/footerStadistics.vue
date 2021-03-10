<template>
  <div @event="value = $event" class="footerStadistics">
    <span class="tittle"> Estadisticas:</span><br />
    <span>Total de tareas: {{ this.totalTasks }}</span
    ><br />
    <span>Tareas realizadas: {{ this.totalTasks - this.todoLength }} </span
    ><br />
    <span>Tareas por realizar: {{ this.todoLength }} </span><br />
  </div>
</template>
<script>
export default {
  inject: ["$todoLength", "$totalTasks"],
  computed: {
    todoLength() {
      return this.$todoLength();
    },
    totalTasks() {
      return this.$totalTasks();
    },
  },
};
</script>
<style lang="scss">
.tittle {
  font-size: 1.5vw;
}
.footerStadistics {
  padding-left: 10vw;
  text-align: left;
}
</style>