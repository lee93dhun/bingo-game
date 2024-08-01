<template>
  <div>
    <AddCell/>
    <GameBoard/>
  </div>
</template>

<script>
import AddCell from './control_panel/AddCell.vue'
import GameBoard from './bingo_board/GameBoard.vue'
export default {
 components: { 
   AddCell,
   GameBoard
 },
 name: 'GameController'
}
</script>

<style>

</style>