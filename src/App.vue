<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">

    <ul>
      <li><router-link to="/">Home</router-link></li>
      <li><router-link to="/tasks">Tasks</router-link></li>
      <li><router-link to="/user/123">User</router-link></li>
    </ul>

    <router-view></router-view>

  </div>
</template>

<script>

export default {
  name: 'app',
  components: {
    
  },
  data: function(){
    return {
      value: 1,
      error: false,
      warning: false
    }
  },

  computed: {
    classObject: function(){
      return {
        'red-error': this.value > 5, 
        'yellow-warning': this.value < 0
      }
    }
  }

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
.red-error{
  background-color: darkred;
}
.yellow-warning{
  text-decoration: underline;
}
</style>
