/* eslint-disable */
<template xmlns:v-on="http://www.w3.org/1999/xhtml">
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>Essential Links</h2>
    <ul>
      <!--{{users}}-->
      <li v-for="user in users">
        {{user.firstname}} {{user.lastname}}
      </li>
      <li>
        <div>
          <input type="text" v-model="input_val">
        </div>
        <div>
          Input Value: <span v-text="input_val"></span>
        </div>
      </li>
        <li>
            <button class="btn btn-primary" v-on:click="counter++">You've clicked this button {{counter}} times!
            </button>
        </li>
      <li><a href="https://vuejs.org" target="_blank">Component1 Docs</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank">Forum</a></li>
      <li><a href="https://chat.vuejs.org" target="_blank">Community Chat</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank">Twitter</a></li>
      <br>
      <li><a href="http://vuejs-templates.github.io/webpack/" target="_blank">Docs for This Template</a></li>
    </ul>
    <h2>Ecosystem</h2>
    <ul>
      <li><a href="http://router.vuejs.org/" target="_blank">vue-router</a></li>
      <li><a href="http://vuex.vuejs.org/" target="_blank">vuex</a></li>
      <li><a href="http://vue-loader.vuejs.org/" target="_blank">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank">awesome-vue</a></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'hello',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      input_val: '',
      counter: 0,
      test: test(),
      users: [ {firstname: 'Sebastian', lastname: 'Eschweiler'},
              {firstname: 'Sebastian213', lastname: 'Eschweiler23423'}]
    }
    function test () {
      console.log('test')
    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
