<template>
    <div>
            <form @submit= "addtodo">
                <input type="text" name="title" v-model="title" placeholder="Add your Todo....">
                <input type="submit" value="Submit" class="btn">
            </form>
    </div>
</template>

<script>
import uuid from 'uuid'
export default {
    name: 'AddtoDo',
    data() {
        return{
            title : ''
        }
    },
    methods: {
        addtodo(e){
            e.preventDefault();
            const newtodo = {
                id:uuid.v4(),
                title: this.title,
                completed: false
            }
            //send to parent by emit
            this.$emit('add-todo',newtodo);

            this.title = '';
        }
    }
}
</script>

<style scoped>
    form{
        display: flex;
    }
    input[type="text"]{
        flex: 10;
        padding: 5px;
    }
    input[type="submit"]{
        flex: 2;
    }
</style>