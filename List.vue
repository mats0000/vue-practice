<template>
    <ul>
      <li v-for="todo in todos" v-bind:key="todo.id" :class="{line: todo.check}"> 
        <input type='checkbox' v-on:click= "updateCheck(todo)"> 
        {{todo.value}}
        <span v-on:click="deleteTodo(todo.id)">   x</span>
      </li>
    </ul>
</template>

<script>

export default {
    props: {
        todos: {
            type: Array,
            required: true,
        }
    },
    methods: {
        updateCheck(todo){
            todo.check = !todo.check;
        },
        deleteTodo(id){
            this.$emit('deletetodo',id);
        },
    }
}

</script>

<style>
.line {
    text-decoration: line-through;
}
</style>