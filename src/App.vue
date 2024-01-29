<template>
  <TodoForm @addNewTodo="addNewTodo"></TodoForm>
  <TodoList
    :todoList="todos"
    @changeTodo="changeTodo"
    @removeTodo="removeTodo"
  ></TodoList>
</template>
<script>
import TodoForm from "./components/TodoForm.vue";
import TodoList from "./components/TodoList.vue";

export default {
  components: { TodoForm, TodoList },
  data() {
    return {
      todos: [
        { id: 1, title: "Позавтракать", completed: true },
        { id: 2, title: "Почистить огурцы", completed: false },
        { id: 3, title: "Помыть кота", completed: true },
      ],
    };
  },
  methods: {
    addNewTodo(title) {
      let newTodo = {
        id: Date.now(),
        completed: false,
        title,
      };
      this.todos.push(newTodo);
    },
    changeTodo(id) {
      this.todos.map((elem) => {
        if (elem.id === id) {
          elem.completed = !elem.completed;
        }
        return elem;
      });
    },
    removeTodo(id) {
      this.todos = this.todos.filter((elem) => elem.id !== id);
    },
  },
};
</script>
<style></style>
