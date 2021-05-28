<template>
    <div>
        <div v-bind:key="todo.id"  v-for="todo in todoslist">
          <Todoitem v-bind:todo="todo"  v-on:delete-todo="$emit('delete-todo',todo.id)"/>
        </div>
    </div>
</template>
<script>
import Todoitem from './Todoitem';
export default {
    name: 'Todos',
    props: ['todoslist'],
    components: {Todoitem}
}
</script>
<style>

</style>