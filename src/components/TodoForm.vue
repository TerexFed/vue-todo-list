<template>
  <div class="input_elem">
    <input
      type="text"
      @keydown.enter="handler"
      v-model="inputVal"
      placeholder="Напишите что вы хотите сделать"
    />
  </div>
</template>
<script>
export default {
  data() {
    return {
      inputVal: "",
    };
  },
  emits: ["addNewTodo"],
  methods: {
    handler() {
      this.$emit("addNewTodo", this.inputVal);
    },
  },
};
</script>
<style>
.input_elem {
  display: flex;
  justify-content: center;
  margin: 20px 400px;
}

.input_elem > input {
  width: 100%;
  height: 30px;
  box-shadow: 5px 5px 5px black;
}
</style>
