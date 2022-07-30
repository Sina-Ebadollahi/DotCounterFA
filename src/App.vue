<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <Navbar />
  <CardComp />
</template>

<script>
import CardComp from "./components/Card-comp.vue";
// import HelloWorld from './components/HelloWorld.vue'
// import CardVue from './components/Card.vue'
import Navbar from './components/Navbar.vue'
export default {
  name: 'App',
  components: {
    CardComp,
    Navbar
},
    mounted(){
      document.getElementById('app').className = 'container-fluid bg-white row min-vh-100 '
    },
}
</script>

<style>
 input{
   outline: unset;
 }
</style>
