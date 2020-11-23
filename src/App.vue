<template>
  <div id="app">
    {{msg}}
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
</style>
