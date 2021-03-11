<template>
  <div>
    <todo-input @todo-added="addToDo"></todo-input>
    <clean-done class="mx-5" @clean="cleanDone"></clean-done>
    <ul class="cont">
      <li class="list-none" v-for="item in todoItems" :key="item.id">
        <todo-item
          :task="item.task"
          :done="item.done"
          :id="item.id"
          @change-input="changeInput"
        ></todo-item>
      </li>
    </ul>
    <portal-target name="destination"></portal-target>
    <todo-footer />
  </div>
</template>
<script>
import uniqueId from "lodash.uniqueid";
import CleanDone from "./cleanDone";
import TodoInput from "./todoInput";
import TodoItem from "./todoItem";
import TodoFooter from "./todoFooter.vue";

export default {
  components: { TodoItem, TodoInput, CleanDone, TodoFooter },
  data() {
    return {
      todoItems: [],
      tasks: 0,
    };
  },
  provide() {
    return {
      $todoLength: () => this.todoLength,
      $totalTasks: () => this.tasks,
    };
  },
  computed: {
    todoLength() {
      return this.todoItems.length;
    },
    totalTasks() {
      return this.tasks;
    },
  },
  methods: {
    cleanDone() {
      this.todoItems = this.todoItems.filter((item) => item.done === false);
    },
    changeInput(_item) {
      this.todoItems = this.todoItems.map((item) => {
        if (_item.id === item.id) return { ...item, done: _item.done };
        return item;
      });
    },
    addToDo(toDoTask) {
      this.todoItems.push({
        id: uniqueId("todo-"),
        task: toDoTask,
        done: false,
      });
      this.tasks += 1;
    },
  },
};
</script>
<style lang="scss">
.cont {
  padding-bottom: 1vh;
  width: 20vw;
  margin: auto;
  display: block;
  text-align: left;
}
.list-none {
  list-style: none;
}
.mx-5 {
  margin-top: 2vh;
  margin-bottom: 2vh;
}
</style>