<template>
    <div  class="todo-item" v-bind:class="{'is-complete':todo.completed}">
        <p>
            <input type="checkbox" v-on:change="markComplete"> 
            {{todo.title}}
            <button @click="$emit('del-todo',todo.id)" class="del" >x</button>
        </p>
    </div>
</template>

<script>
export default {
    name:"Todoitem",
    props: ["todo"],
    methods: {
        markComplete() {
            this.todo.completed = !this.todo.completed;
        }
    }
}
</script>
<style scoped>
    .todo-item {
        text-decoration: white;
        padding:10px;
        border-bottom: 1px white dotted;
    }
    .is-complete{
        text-decoration: line-through;

    }
    .del{
        background: red;
        color: white;
        border-color: red;
        border: 50px 50px;
        border-radius: 50%;
        cursor: pointer;
        float: right;
    }
</style>