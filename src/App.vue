<template>
  <p>HELLO THERE</p>
  <sign-up></sign-up>
  <p>HI ANYONE??</p>

</template>

<script>
import SignUp from './components/SignUp.vue'

export default {
  name: 'App',
  components: {
    SignUp
    
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
body{
  background-color: #e7e4e4;
  margin: 0;
  font-size: large;
}
</style>
