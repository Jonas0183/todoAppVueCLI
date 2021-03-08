<template>
  <div>
    <todo-input @todo-added="addToDo"></todo-input>
    <ul>
      <li class="list-none" v-for="item in todoItems" :key="item.id">
        <todo-item
          :task="item.task"
          :done="item.done"
          :id="item.id"
          @change-input="changeInput"
        ></todo-item>
      </li>
    </ul>
    <clean-done @clean="cleanDone"></clean-done>
  </div>
</template>
<script>
import uniqueId from "lodash.uniqueid";
import CleanDone from "./cleanDone";
import TodoInput from "./todoInput";
import TodoItem from "./todoItem";

export default {
  components: { TodoItem, TodoInput, CleanDone },
  name: "App",
  data() {
    return {
      todoItems: [],
    };
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
    },
  },
};
</script>
<style lang="scss">
.list-none {
  list-style: none;
}
</style>