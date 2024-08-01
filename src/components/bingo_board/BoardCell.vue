<template>
  <div class="cell" @click="selectNum()">
    <p>{{ num }}</p>
  </div>
</template>

<script>
export default {
    name: 'BoardCell',
    data() {
      return{
        num: ' '
      }
    },
    methods :  {
      selectNum(){
        if(this.num==' '){
          this.num = 'Test';
        }else{
          this.num = ' ';
        }
      } 
    }
};




</script>

<style>
    .cell{
        border: 1px solid #FFF;
        width: 70px;
        height: 70px;
    }
    .cell:hover{
      border: 1px solid #8b0000;
    }
    
</style>