<template>
  <form @submit.prevent="onSubmit">
    <label for="new-todo-input"> ¿Qué nuevas tareas hay por hacer? </label>
    <input
      type="text"
      id="new-todo-input"
      name="new-todo"
      autocomplete="off"
      v-model.lazy.trim="task"
    />
    <button type="submit">Añadir</button>
  </form>
</template>
<script>
export default {
  methods: {
    onSubmit() {
      if (this.task === "") return;

      this.$emit("todo-added", this.task);
      this.task = "";
    },
  },
  data() {
    return {
      task: "",
    };
  },
};
</script>
<style lang="">
</style>