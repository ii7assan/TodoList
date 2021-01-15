<template>
    <div id="">
        <div v-for="todo in todos" v-bind:key="todo.id">
            <!-- <h3>{{todo.title}}</h3> -->
            <Todoitem  v-bind:todo = "todo"  v-on:del-todo="$emit('del-todo',todo.id)"/>
        </div>
    </div>
</template>
<script>
import Todoitem from './Todoitem.vue'
export default {
    name:"Todos",
    components: {
        Todoitem
    },
    props: ["todos"]
}
</script>

<!-- scope means only in this component the style will be used-->
<style scoped>

</style>