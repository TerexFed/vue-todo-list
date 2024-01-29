<template>
    <div>
        <div v-for="(todoItem, ind) in todoList" :key="ind">
            <TodoItem
                :id="todoItem.id"
                :title="todoItem.title"
                :completed="todoItem.completed"
                @change="handleChangeTodo"
                @remove="handleRemoveTodo"
            ></TodoItem>
        </div>
    </div>
</template>
<script>
import TodoItem from './TodoItem.vue';
export default {
    props: ['todoList'],
    components: { TodoItem },
    emits: ['changeTodo', 'removeTodo'],
    methods: {
        handleChangeTodo(id){
            this.$emit("changeTodo", id);
        },
        handleRemoveTodo(id){
            this.$emit("removeTodo", id);
        }
    },
}
</script>
<style>
    
</style>