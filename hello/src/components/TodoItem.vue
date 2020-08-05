<template>
    <div class="todoitem" v-bind:class="{'is-complete':todo.completed}">
        <p class="content"> 
        <input type="checkbox" v-on:change="markComplete">
        {{todo.title}}
        <button @click="$emit('del-todo', todo.id)" class="del">X</button>
        </p>
    </div>
</template>

<script>
export default{
    name: "TodoItem",
    props: ["todo"],
    methods: {
        markComplete(){
            this.todo.completed = !this.todo.completed;
        }
    }
}
</script>

<style scoped>
    .todoitem {
        padding: 10px;
        border: 3px dotted black;
        border-radius: 5px;
        margin: 10px 25%;
        display: flex;
    }
    .content{
        margin: auto;
    }
    .del{
        border: 1px red solid;
        border-radius: 50px;
        background-color: red;
    }
    .is-complete{
        text-decoration: line-through;
    }
</style>