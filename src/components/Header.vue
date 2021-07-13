<template>
  <header>
      <div class="container">
          <div class="logo h1 my-2 font-weight-bold">
              Boolflix
          </div>
          <input class="my-3 fs-2 p-3" type="text"
          placeholder="Search Movies..."
          v-model="searchText"
          @keyup="$emit('ricerca',searchText)">
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
@import "@/style/utilities.scss";
@import "../style/vars.scss";

header {
    display: flex;
    justify-content: space-around;
    height: 70px;
    width: 100%;
    background-color: #000000;

    .container {
        display: flex;
        justify-content: space-between;

        .logo {
            
            display: flex;
            color: whitesmoke;
        }

        input {
            border-radius: 10px;
            border: 2px solid grey;
        }

    }

    

    
}

</style>