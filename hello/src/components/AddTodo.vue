<template>
    <div>
        <form @submit="addTodo">
            <input type="text" v-model="title" name="title" placeholder="Add Todo">
            <input type="submit" value="Submit" class="btn">
        </form>
    </div>
</template>


<script>
export default{
    name: "AddTodo",
    data(){
        return{
            title: ''
        }
    },
    methods: {
        addTodo(e){
            e.preventDefault();
            const newTodo = {
                id: Math.random(),
                title: this.title,
                completed: false
            }
            this.$emit('add-todo', newTodo);
        }
    }
}
</script>

<style scoped>
    form{
        display: flex;
        margin: 0 25%;
    }
    input{
        flex:2;
    }
    .btn{
        flex: 1;
        color: white;
        background-color: lightblue;
    }
</style>