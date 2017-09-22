<template>
    <div id="app">
        <h1 class="ui dividing centered header">{{message}}</h1>
        <div class='ui three column centered grid'>
            <div class='column'>
                <!--<todo-list v-bind:todos="todos"></todo-list>-->
                <!--<create-todo v-on:create-todo="createTodo"></create-todo>-->
                <!--<testing v-for="item in todos" v-bind:todo="item"></testing>-->

            </div>
        </div>
        <search  v-on:search="getPosts"></search>
        <ny-time  v-bind:post="results"></ny-time>

    </div>
</template>

<script>
    //    import sweetalert from 'sweetalert';
    //    import TodoList from './components/TodoList';
    //    import CreateTodo from './components/CreateTodo';
    //    import Testing from './components/TestingA.vue';
    import NyTime from './components/NyTime.vue';
    import Search from './components/Search.vue';

    export default {
        name: 'app',
        components: {
//            TodoList,
//            CreateTodo,
            NyTime,Search
        },
        data() {
            return {
                message: "NYTime POST",
                results: []
//                results: [
//                    {title: "the very first post", abstract: "lorem ipsum some test dimpsum"},
//                    {title: "and then there was the second", abstract: "lorem ipsum some test dimsum"},
//                    {title: "third time's a charm", abstract: "lorem ipsum some test dimsum"},
//                    {title: "four the last time", abstract: "lorem ipsum some test dimsum"}
//
//                ],
            };
        },
        mounted() {
            var vm = this
            axios.get('https://jsonplaceholder.typicode.com/posts/2')
                .then(function (response) {
                    vm.results = response.data
                })
        },
        methods: {
            getPosts(text) {
                console.log("App"+text.title)
//                let url = 'https://jsonplaceholder.typicode.com/posts/'+text.title;
                var vm = this
                axios.get('https://jsonplaceholder.typicode.com/posts/'+text.title)
                    .then(function (response) {
                        if (response.data==""){
                            console.log("Null");
                        }
                        vm.results = response.data
                    })
            }
        },
//        computed: {
//            processedPosts() {
//                let posts = this.results;
//
//                // Add image_url attribute
////                posts.map(post => {
////                    let imgObj = post.multimedia.find(media => media.format === "superJumbo");
////                    post.image_url = imgObj ? imgObj.url : "http://placehold.it/300x200?text=N/A";
////                });
//                let i, j, chunkedArray = [], chunk = 4;
//                for (i = 0, j = 0; i < posts.length; i += chunk, j++) {
//                    chunkedArray[j] = posts.slice(i, i + chunk);
//                }
//                return chunkedArray;
//            },
//        methods: {
//            createTodo(newTodo) {
//                console.log(newTodo);
//                this.todos.push(newTodo);
////                sweetalert('Success!', 'To-Do created!', 'success');
//            },
//        },
        };
</script>