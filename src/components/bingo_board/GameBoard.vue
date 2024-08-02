<template>
<div class="game-board-wrapper">
    <div>{{playerName}}</div>
    <div class="game-board">
    <BoardCell 
        v-for="(cell, index) in boardCells"
        :key="index"
        :selectedItems = "selectedItems"
        @update-selected="updateSelected"
        :index="index"
    />
    </div>
</div>
</template>

<script>
import BoardCell from './BoardCell.vue';

export default {
    components: { BoardCell },
    name: 'GameBoard',
    props: {
        playerName:{
            type: String,
            required: true
        },
        playerCnt:{
            type: Number,
            required: true
        }
    },
    data() {
        return{
            selectedItems: [],
            boardCells: Array(9).fill(null)
        };
    },
    methods: {
        updateSelected(index, selectedItem){
            console.log("recive==",index, selectedItem);
            this.$set(this.selectedItems, index, selectedItem); // set(업데이트 할 배열/ key / value)
            console.log('updated selectedItems', this.selectedItems);
            this.$set(this.boardCells, index, selectedItem);
        }
    }
}
</script>

<style>
    .game-board {
        display: inline-grid;
        grid-template-columns: repeat(3,70px); /* 3x3 그리드 */
        gap: 5px;
        margin: 15px;
    }
   
    .game-board-wrapper{
        display: inline-block;
    }
</style>