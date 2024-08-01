<template>
  <v-app>
  <div>
    
    <v-container>
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

  


/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
</style>
