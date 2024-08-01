<template>
  <div>
    <v-btn>+ Bingo Board</v-btn>
    <GameBoard/>
  </div>
</template>

<script>
import GameBoard from './bingo_board/GameBoard.vue'
export default {
 components: { 
   GameBoard
 },
 name: 'GameController'
}

</script>

<style>

</style>