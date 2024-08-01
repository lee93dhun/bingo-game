<template>
<div class="game-board">
  <BoardCell/>
</div>
</template>

<script>
import BoardCell from './BoardCell.vue'
export default {
    components: { BoardCell },
    name: 'GameBoard'
}
</script>

<style>
    .game-board {
        display: grid;
        grid-template-columns: repeat(3, 100px); /* 3x3 그리드 */
        gap: 10px;

    }
</style>