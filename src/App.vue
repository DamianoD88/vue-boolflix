<template>
  <div id="app">
    <!-- app.vue prende l'emit inviato da Header richiamando una funzione(researchMovie)
    passandogli quel parametro (nei methods)* -->
    <Header @ricerca="researchMovie"/>
    <Main :films="filmsArray" :range= "rangeRequired"/>
  </div>
</template>

<script>
import axios from "axios";
import Header from "@/components/Header.vue";
import Main from "@/components/Main.vue";

export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data() {
    return {
      apiUrl: 'https://api.themoviedb.org/3/search/movie',
      tvUrl: 'https://api.themoviedb.org/3/search/tv',
      apikey: '20f2e48348860ecfa91f99da107394ca',
      language: 'it-IT',
      filmsArray: '',
      range: '',
      rangeRequired:'',
      tvArray: ''
      
      
      

    }
  },
  methods: {
    // text è un segnaposto di searchText di Header, fa la chiamata sulla base del parametro searchText di Header*
    researchMovie(text) {
      this.range = text;

      // Metodo all
      // metto tutto params in una variabile const per quando mi serve usarla chiamandola request
      const request = {
            params: {
                   api_key: this.apikey,
                   language: this.language,
                   query: text
                 }
      };

      axios
          .all([
            // dentro all le due chiamate ma volendo tutte quelle che si vogliono 
              axios.get(this.apiUrl, request),
              axios.get(this.tvUrl, request)
          ])
          // quando ci sono più chiamate (get) posso utilizzare axios.spread
          .then(axios.spread(respMovie, respTv))
          // respMovie rappresenta la prima chiamat api
          // respTv rappresenta la seconda chiamata api
      
        // axios
        //     .get(this.apiUrl, {
        //         
        //     })
        //     .then( response => {
        //        console.log(response.data.results);
        //        this.filmsArray = response.data.results;
        //     });
        // console.log(text);
    }
  }
}
</script>

<style lang="scss">
@import "@/style/utilities.scss";
@import "@/style/general.scss";


</style>
