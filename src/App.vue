<template>
  <v-app>
  <div>
    <v-container class="container">
      <h1>Bingo</h1>
      <GameController/>
    </v-container>
  </div>
  </v-app>
</template>

<script>
import GameController from './components/GameController.vue'
  export default {
    components: { GameController },
    name:"App"
  }
</script>

<style>
  .container{
    width: 900px;
    padding: 50px;
  }
</style>
