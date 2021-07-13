<template>
  <header>
      <div class="container">
          <div class="logo">
              Boolflix
          </div>
          <input type="text"
          placeholder="Search Movies"
          v-model="searchText"
          @keyup="$emit('ricerca', searchText)">
      </div>
  </header>
</template>

<script>
export default {
    name: "Header",
    data() {
        return {
            searchText: ''
        }
    }
};
</script>

<style scoped lang="scss">
@import "@/style/utilities";
@import "../styles/vars";


</style>