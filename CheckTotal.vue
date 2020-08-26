
<template>

<p>checked: {{checkedTotal}}</p>

    
</template>

<script>

export default {
    props: {
        todos: {
            type: Array,
            required: true,
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
</style>