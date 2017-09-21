<template>
    <div class="columns medium-12" >
        <div class="card">
            <!--{{post}}-->
            <div class="card-divider">
                {{post.title}} <p>Post ID is </p>{{post.id}}
            </div>
            <div class="card-section">
                <p>{{post.body}}.</p>
            </div>
        </div>
    </div>

</template>
<script>
    export default {
        props: ['post']
    }
</script>