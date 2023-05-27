<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld/>
  <Test/>
  <AddList/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Test from './components/Test.vue'
import AddList from './components/AddList.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    Test,
    AddList
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
