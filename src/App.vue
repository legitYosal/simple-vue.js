<template>
  <div id="app">
    <div v-if="show_msg">{{msg}}</div>

    <div v-if="show_msg">true</div>
    <div v-else-if="!show_msg">false</div>
    <div v-else>none</div>

    <div v-for="(item, index) in msg_list" :key="index">
      <hr>
      <h3><span>{{index + 1}} </span>{{item}}</h3>
    </div>

    <button @click="toggle_show_msg($event)">toggle me</button>

    <hr>
    <hr>
    <post-comp 
      @change_text="change_post_text"
      :text="post_text" />
  </div>
</template>

<script>
import Post from './components/Post.vue'

export default {
  name: 'App',
  components: {
    'post-comp': Post,
  },
  data() {
    return {
      msg: 'Hello World!',
      show_msg: true,
      msg_list: ['hi', 'hola', 'hallow',  'salama'],
      post_text: 'this is a random string for post to show off',
    }
  }, 
  methods: {
    toggle_show_msg() {
      this.show_msg = !this.show_msg
    },
    change_post_text(new_text) {
      this.post_text = new_text
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
span {
  font-size: 16px;
}
</style>
