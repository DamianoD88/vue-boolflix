<template>
  <div class="card" >

    <img v-if="info.poster_path !== null"
     :src="`https://image.tmdb.org/t/p/w342/${info.poster_path}`" 
     :alt="info.title == null ? info.name : info.title">

    <img v-else 
    src="../assets/img/not_found.png" 
    :alt="info.title == null ? info.name
    :info.title">

    <ul>
      <li><strong>Titolo: </strong> {{ info.title == null ? info.name : info.title }} </li>
      <li><strong>Titolo originale: </strong> {{ info.original_title || info.original_name }}      </li>
      <li v-if="flags.includes(info.original_language)"><strong>Lingua originale: </strong> {{ info.original_language }} 
      <!-- con il require posso fare l'import delle immagini nel file -->
        <img :src="require(`../assets/${ info.original_language }.png`)" :alt="info.original_language">

      </li>
      <li v-else>
        <strong>Lingua originale: </strong> {{ info.original_language }}
      </li>

      <li><strong>Titolo: </strong> {{ info.vote_average }} </li>
    </ul>
  </div>
</template>

<script>
export default {
    name: "Card",
    // Card ha preso l'oggetto info da Main
    props: ["info"],
    data(){
      return {
          flags: ["en", "it", "sp", "usa", "fr", "nz", "ja"],
          poster: ["",]
      }
    }
      
    
};

</script>

<style scoped lang="scss">
@import "@/style/utilities.scss";
@import "../style/vars.scss";


img {
      width: 50px;
}

</style>