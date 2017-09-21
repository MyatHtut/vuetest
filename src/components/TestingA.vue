<template xmlns:v-on="http://www.w3.org/1999/xhtml">
<div>

    <h1 >Hello{{todo.title}}</h1>
</div>
</template>
<script>
    export default {
        name:'testing',
        props: ['todo'],
    }
</script>