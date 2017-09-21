<template xmlns:v-on="http://www.w3.org/1999/xhtml">
    <section class="callout secondary">
        <h5 class="text-center">Filter by Category</h5>
        <form>
            <div class="row">
                <div class="large-6 columns">
                    <input v-model="titleText" type='text'>
                    <!--<select v-model="section">-->
                    <!--<option v-for="section in sections" :value="section">{{ section }}</option>-->
                    <!--</select>-->
                </div>
                <div class="medium-6 columns">
                    <a v-on:click="sendForm()" class="button expanded">Retrieve</a>
                </div>
            </div>
        </form>
    </section>
</template>
<script>
    export default {
        name: 'search',
        data(){
            return {
                titleText: '',
            };
        },
        methods: {
            sendForm(){
                const title = this.titleText;
                this.$emit('search', {
                    title
                });
                console.log("Text" + this.titleText);

            },
        }
//        props: ['todo'],
    }
</script>