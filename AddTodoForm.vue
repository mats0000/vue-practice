<template>
  <div>
    <input type="text" v-on:keyup.enter = "add">
    <ul>
      <li v-for="todo in todos" v-bind:key="todo.id" :class="{line: todo.check}"> 
        <input type='checkbox' v-on:click= "updateCheck(todo)"> 
        {{todo.value}}
        <span v-on:click="deleteTodo(todo.id)">   x</span>
      </li>
    </ul>
    <p>total: {{todos.length}}</p>
    <p>checked: {{checkedTotal}}</p>
  </div>
</template>


<script>

export default {
  data () {
    return {
      todos: [],
      index: 0
    }
  },
  methods: {
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
    deleteTodo(id){
      this.todos = this.todos.filter(x => x.id !== id);
    },
    updateCheck(todo){
      todo.check = !todo.check;
    }
  },
  computed: {
    checkedTotal(){
      return this.todos.filter(x=> x.check === true).length;
    }
  }
}

</script>
<style>
.line {
    text-decoration: line-through;
}
</style>