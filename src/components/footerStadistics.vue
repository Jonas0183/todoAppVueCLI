<template>
  <div class="footerStadistics">
    <span class="tittle"> Estadisticas:</span><br />
    <span>Total de tareas: {{ this.totalTasks }}</span
    ><br />
    <span>Tareas realizadas: {{ this.totalTasks - this.todoLength }} </span
    ><br />
    <span>Tareas por realizar: {{ this.todoLength }} </span><br />
    <!-- Parte que se inyecta en el listBody -->
    <portal to="destination">
      <p>
        Porcentaje de tareas realizadas hoy :
        {{ ((this.totalTasks - this.todoLength) / this.totalTasks) * 100 }}%
      </p>
    </portal>
    <!-- hasta aqui -->
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