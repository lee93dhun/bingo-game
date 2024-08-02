<template>
  <div>
    <v-btn @click="addPlayer">+ PLAYER</v-btn>
    <v-btn @click="callNum">CALL</v-btn>
    <v-btn @click="resetGame">RESET</v-btn>
    <div>
      <GameBoard 
        v-for="(player, index) in playerNums"
        :key="index"
        :playerName="'PLAYER '+(index+1)"
        :playerCnt = "player"
      />
    </div>
  </div>
</template>

<script>
import GameBoard from './bingo_board/GameBoard.vue'
// import EventBus from "../EventBus";
export default {
 components: { 
   GameBoard
 },
 name: 'GameController',
 data(){
  return{
    playerNums: []
  };
 },
 methods: {
    addPlayer(){
      if(this.playerNums.length < 5){
        this.playerNums.push(this.playerNums.length + 1);
      }else{
        alert("플레이어는 최대 5명 입니다.")
      }
    },
    callNum(){
      if(this.playerNums.length < 2 ){
        alert('플레이어 최소 2명이 있어야 합니다.')
      }else{
        alert('GAME START')
      }
    },
    blankCellChk(){

    },
    resetGame(){
      confirm('게임을 초기화 합니다.');
    }

 }
 
 
}

</script>

<style>
 
</style>