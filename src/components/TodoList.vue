<template>
    <div class="TodoList">
        <!--         JavaScript expressions in Vue are enclosed in double curly brackets.-->
        <p>Completed Tasks: {{todos.filter(todo => {return todo.done === true}).length}}</p>
        <p>Pending Tasks: {{todos.filter(todo => {return todo.done === false}).length}}</p>
        <Todo v-on:delete-todo="deleteTodo" v-for="todo in todos" v-bind:key="todo.id" v-bind:todo="todo"/>
    </div>
</template>

<script type="text/javascript">
    import Todo from "@/components/Todo";
    export default {
        components: {
            Todo
        },
        props: {
            'todos': Object //The TodoList component has to declare the properties it will accept
        },
        methods: {
            deleteTodo(todo) {
                const todoIndex = this.todos.indexOf(todo);
                this.todos.splice(todoIndex, 1);
            },
        }
    };
</script>
