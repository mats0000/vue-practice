<template>
  <div> 
    <InputTodo @addtodo = "add"></InputTodo>
    <List :todos = "todos" @deletetodo="deleteTodo"></List>
    <ListTotal :todos = "todos"></ListTotal>
    <CheckedTotal :todos = "todos"></CheckedTotal>
  </div>
  
</template>

<script>

import InputTodo from "./InputTodo.vue";
import List from "./List.vue";
import ListTotal from "./ListTotal.vue";
import CheckedTotal from "./CheckTotal";


export default {
  name: "App",
  components: {
    InputTodo,
    List,
    ListTotal,
    CheckedTotal
  },
  data() {
    return {
      todos: [],
      index: 0
    }
  },
  methods: {
    deleteTodo(id){
      this.todos = this.todos.filter(x => x.id !== id);
    },
    add(event){
      const text = event.target.value;
      if (text === ""){
        return;
      }
      this.todos.push({
        id: this.index,
        value: text,
        check: false
      });
      event.target.value = "";
      this.index++;
    },
  }
};
</script>

<style>
</style>
