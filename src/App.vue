<template>
  <div id="app">
    <div v-if="show_msg">{{msg}}</div>

    <div v-if="show_msg">true</div>
    <div v-else-if="!sho_msg">false</div>
    <div v-else>none</div>

    <div v-for="(item, index) in msg_list" :key="index">
      <hr>
      <h3><span>{{index + 1}} </span>{{item}}</h3>
    </div>

    <button @click="toggle_show_msg($event)">toggle me</button>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      msg: 'Hello World!',
      show_msg: true,
      msg_list: ['hi', 'hola', 'hallow',  'salama'],
    }
  }, 
  methods: {
    toggle_show_msg() {
      this.show_msg = !this.show_msg
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
