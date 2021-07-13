<template>
  <div id="app">
    <Header/>
    <Main/>
    <img alt="Vue logo" src="./assets/logo.png">
    <h2>BoolFlix</h2>
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  </div>
</template>

<script>
import axios from "axios";
import Header from "@/components/Header.vue";
import Main from "@/components/Main.vue";


/* import HelloWorld from './components/HelloWorld.vue' */

export default {
  name: 'App',
  components: {
    // HelloWorld
    Header,
    Main
    

  }
}
</script>

<style lang="scss">
@import '@/style/general.scss';


</style>
