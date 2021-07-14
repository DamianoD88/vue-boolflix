<template>
  <div class="card">
    <ul>
      <li><strong>Titolo: </strong> {{info.title}} </li>
      <li><strong>Titolo originale: </strong> {{info.original_title}} </li>
      <li><strong>Lingua: </strong> {{info.original_language}} </li>
      <li><strong>Titolo: </strong> {{info.vote_average}} </li>
    </ul>
  </div>
</template>

<script>
export default {
    name: "Card",
    // Card ha preso l'oggetto info da Main
    props: ["info"],
    
};

</script>

<style scoped lang="scss">
@import "@/style/utilities.scss";
@import "../style/vars.scss";

</style>