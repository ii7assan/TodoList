<template>
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
        <p>
            <input type="checkbox" v-on:change="markComplete">
            {{todo.title}}
            <button class="del" @click="$emit('del-todo',todo.id)">x</button>
            <input type="text" name="" id="edit" class="id" >
            </p>
    </div>
</template>
<script>
export default {
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
    .todo-item{
        background: #f4f4f4;
        padding: 10px;
        border-bottom: 1px #ccc dotted;
          transition: 1s all ease-in;
    }
    .is-complete{
        text-decoration: line-through;
      
    }
    .del{
        background: #ff0000;
        color: #fff;
        border: none;
        padding: 5px 9px;
        border-radius: 50%;
        cursor: pointer;
        float: right;
    }
    .edit{
        float: right;
        padding: 3px 5px;
    }
</style>