<template>
    <div>
       <div v-for="(todo,id) in todos" :key="id">
           <Todoitem v-bind:todo="todo" v-on:del-todo="$emit('del-todo',todo.id)" />
       </div>
    </div>
</template>
<script>
import Todoitem from "./Todoitem"
export default {
    name:"Todos",
    components: {
        Todoitem
    },

    props: ["todos"]
}
</script>
<style scoped>

</style>