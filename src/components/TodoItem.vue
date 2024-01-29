<template>
  <div
    @click="handleChange"
    @dblclick="handleRemove"
    v-if="completed"
    style="background-color: green"
    class="todo_item"
  >
    <h2>
      {{ title }}
    </h2>
  </div>
  <div
    v-else
    @click="handleChange"
    @dblclick="handleRemove"
    style="background-color: red"
    class="todo_item"
  >
    <h2>
      {{ title }}
    </h2>
  </div>
</template>
<script>
export default {
  props: ["id", "title", "completed"],
  emits: ["change", "remove"],
  methods: {
    handleChange() {
      this.$emit("change", this.id);
    },
    handleRemove() {
      this.$emit("remove", this.id);
    },
  },
};
</script>
<style>
.todo_item {
  display: flex;
  flex-direction: column;

  margin: 20px 170px;
  padding: 10px;

  outline: 2px solid black;
  box-shadow: 5px 5px 5px black;
}
</style>
