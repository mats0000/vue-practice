<template>

<p>total: {{totalList}}</p>

    
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
        totalList(){
            return this.todos.length
        }
    }
}

</script>

<style>
</style>