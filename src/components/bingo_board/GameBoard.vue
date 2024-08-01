<template>
<div class="game-board">
  <BoardCell v-for="index in 9"
    :key="index"
  />
</div>
</template>

<script>
import BoardCell from './BoardCell.vue'
export default {
    components: { BoardCell },
    name: 'GameBoard',
    data() {
        return{
            cell: BoardCell
        }
    }
    
}
</script>

<style>
    .game-board {
        display: grid;
        grid-template-columns: repeat(3,70px); /* 3x3 그리드 */
        gap: 10px;

    }
</style>