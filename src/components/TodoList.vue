<template>
    <div>
        <ul>            
            <Todoitem
            v-for="(todo, i) in todos"
            :todo="todo"
            :index="i"
            :key="todo.id"
            v-on:remove-todo="removeTodo" 
            />
        </ul>
    </div>
</template>

<script>
import Todoitem from '@/components/Todoitem'
export default {
    name: 'TodoList',
    props: ['todos'],
    components: {
        Todoitem,
    },
    methods: {
        removeTodo(id){
            this.$emit('remove-todo', id)
        }
    }
}
</script>

<style scoped>
    ul{
        list-style: none;
        margin: 0;
        padding: 0;
    }
</style>