<template>

<input type="text" v-on:keyup.enter = "add">
    
</template>

<script>

export default {
    methods: {
        add(){
            this.$emit('addtodo',event); 
        }
    }
}

</script>

<style>
</style>