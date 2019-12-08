<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Hello to all coders"/>

    <tasks/>

    <!-- <p :class="{ 'red-error': error, 'yellow-warning': warning }">123</p> another way -->
    <p :class="classObject">{{ value }}</p>
    <p :style="{ fontSize:(value*10) + 'px' }">{{ value }}</p>
    
    <button type="button" @click="value++">+</button>
    <button type="button" @click="value--">-</button>

    <button type="button" @click="error = ! error">Error</button>
    <button type="button" @click="warning = ! warning">Warning</button>

  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';
import Tasks from './components/Tasks.vue';

export default {
  name: 'app',
  components: {
    HelloWorld,
    Tasks
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
