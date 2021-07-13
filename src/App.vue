<template>
  <div id="app">
    <Header @ricerca="researchMovie"/>
    <Main />
   <!--  <img alt="Vue logo" src="./assets/logo.png"> -->
    
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
  },
  data() {
    return {
      apiUrl: 'https://api.themoviedb.org/3/search/movie',
      apikey: '20f2e48348860ecfa91f99da107394ca',
      language: 'it-IT',
      filmsArray: []

    }
  },
  methods: {
    researchMovie(text) {
        axios
            .get(this.apiUrl, {
                params: {
                  api_key: this.apikey,
                  language: this.language,
                  query: text
                }
            })
            .then( response => {
               console.log(response.data.results);
               this.filmsArray = response.data.results;
            });
        console.log(text);
    }
  }
}
</script>

<style lang="scss">
@import "@/style/utilities.scss";
@import "@/style/general.scss";


</style>
