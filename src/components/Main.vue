<template>
  <main>
      <div class="container">
        <div class="search">
            <h2>Risultato ricerca: {{ range }} </h2>
            <div class="cards">
                <!-- passo dal padre Header al figlio Main la props :film -->
                <Card v-for="film in films" :key="film.id" 
                :info="film"/>
            </div>
        </div> 
      </div>
     
  </main>
</template>

<script>

import Card from "@/components/Card.vue";

export default {
    name: "Main",
    components: {
        Card,

    },
    props: ["films", "range"] 
};
</script>

<style scoped lang="scss">
@import "@/style/utilities.scss";
@import "../style/vars.scss";


</style>