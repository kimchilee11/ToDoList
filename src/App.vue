<template>
  <div id="app">
      <ToDoList />
  </div>
</template>

<script>
import DemoSlot from './components/DemoSlot'
import ToDoList from './components/ToDoList'
export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  components:{
    DemoSlot,
    ToDoList
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
  /* margin-top: 60px; */
  /* border: 4px solid #2c3e50 ; */
  /* height: 400px; */
}
</style>
