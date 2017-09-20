<template>
    <div>
        <p class="tasks">Completed Tasks: {{todos.filter(todo => {return todo.done === true}).length}}</p>
        <p class="tasks">Pending Tasks: {{todos.filter(todo => {return todo.done === false}).length}}</p>
        <todo v-for="todo in todos" :todo.sync="todo" v-bind:todo="todo" v-on:delete-todo="deleteTodo" v-on:complete-todo="completeTodo"></todo>
    </div>
</template>
<script type="text/javascript">
    import Todo from './Todo.vue'

    export default {
        props: ['todos'],
        components: {
            Todo,
        },
        methods: {
            deleteTodo(todo) {
                const todoIndex = this.todos.indexOf(todo);
                console.log('IndexOf', todoIndex);
                this.todos.splice(todoIndex, 1);
            },
            completeTodo(todo) {
                const todoIndex = this.todos.indexOf(todo);
                this.todos[todoIndex].done = true;
            },
        }
    };
</script>
<style scoped>
    p.tasks {
        text-align: center;
    }
</style>