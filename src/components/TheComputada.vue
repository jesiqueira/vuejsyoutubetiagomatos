<template>
    <br /><br />
    <h1>Propriedades computadas</h1>
    <div>
        {{ fullName }}
    </div>
    <h4>Incompletas</h4>
    <div v-for="todo in unCompletedTodos" :key="todo.id">
        {{ todo.title }} - <span>{{ todo.completed }}</span>
    </div>
    <h3>Comletadas</h3>
    <div v-for="todo in completedTodos" :key="todo.id">
        {{ todo.title }} - <span>{{ todo.completed }}</span>
    </div> 
    <h3>Todas</h3>
    <div v-for="todo in todos" :key="todo.id">
       <input type="checkbox" v-model="todo.completed">{{ todo.title }}
    </div>
</template>

<script>
export default {
    name: 'TheComputada',
    data() {
        return {
            user: {
                firstname: 'Edmar Siqueira',
                lastname: 'Siqueira',
            },
            todos: [
                {
                    userId: 1,
                    id: 1,
                    title: 'delectus aut autem',
                    completed: false,
                },
                {
                    userId: 1,
                    id: 2,
                    title: 'quis ut nam facilis et officia qui',
                    completed: false,
                },
                {
                    userId: 1,
                    id: 3,
                    title: 'fugiat veniam minus',
                    completed: false,
                },
                {
                    userId: 1,
                    id: 4,
                    title: 'et porro tempora',
                    completed: true,
                },
            ],
        };
    },
    methods: {},
    computed: {
        fullName() {
            return `${this.user.firstname} ${this.user.lastname}`;
        },

        unCompletedTodos() {
            return this.todos.filter((todo) => !todo.completed);
        },
        completedTodos() {
            return this.todos.filter((todo) => todo.completed);
        },
    },
};
</script>

<style></style>
