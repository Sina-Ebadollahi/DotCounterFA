<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <section :class="bg">
    <Navbar :appTheme="theme" :themeChanger="themeChanger" :changeLang="changeLang" />
  <CardComp :appTheme="theme"  />
  </section>
</template>

<script>
import CardComp from "./components/Card-comp.vue";
import Navbar from './components/Navbar.vue'
export default {
  data(){
    return{
      theme:'Light',
      bg: "container-fluid  row min-vh-100 bg-dark",
      lang: "Fa"
    }
  },
  name: 'App',
  components: {
    CardComp,
    Navbar
},
    methods:{
      themeChanger(newVal){
        this.theme = newVal;
        this.checkBackground()
      },
      checkBackground(){
        if(this.theme == "Dark"){
        this.bg = "container-fluid  row min-vh-100 bg-white"
      }
      else if(this.theme == "Light"){
        this.bg = "container-fluid row min-vh-100 bg-dark"
      }
      
      },
      changeLang(newLang){
        console.log(this.lang);
                this.lang = newLang;
            }
      },

      
    
    
}
</script>

<style>
 input{
   outline: unset;
 }
</style>
