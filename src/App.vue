<template>
    <div id="app">
        <img alt="Vue logo" src="./assets/logo.png">
        <CreateTodo v-on:click="addTodo"/>
        <TodoList v-bind:todos="todos"/>
    </div>
</template>

<script>
    import TodoList from './components/TodoList.vue'
    import CreateTodo from "@/components/CreateTodo";

    export default {
        name: 'app',
        components: {
            TodoList, //Reference to the To-do list component in the components property
            CreateTodo
        },
        methods: {
            addTodo(title, project) {
                this.todos.push({
                    title,
                    project,
                    done: false
                });
            }
        },
        data() {
            return {
                todos: [{
                    id: 1,
                    title: 'Todo A',
                    project: 'Project A',
                    done: false,
                }, {
                    id: 2,
                    title: 'Todo B',
                    project: 'Project B',
                    done: true,
                }, {
                    id: 3,
                    title: 'Todo C',
                    project: 'Project C',
                    done: false,
                }, {
                    id:4,
                    title: 'Todo D',
                    project: 'Project D',
                    done: false,
                }],
            };
        },
    }
</script>

<style>
    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }
</style>
