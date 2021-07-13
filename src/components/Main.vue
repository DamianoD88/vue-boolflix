<template>
  <main>
      <div class="search">
          <h2>Risultato ricerca: </h2>
          <div class="cards">
              <Card />
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
    }
}
</script>

<style scoped lang="scss">
@import "@/style/utilities";
@import "../styles/vars";


</style>