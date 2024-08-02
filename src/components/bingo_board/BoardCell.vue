<template>

  <div class="cell">
    <v-select
      v-model="selected"
      :items="allItems"
      item-text="name"
      item-value="id"
      @change="handleChange"
      class="no-arrow-select"
    ></v-select>
  </div>
   
</template>

<script>
export default {
    name: 'BoardCell',
    props:{
      selectedItems:{
        type: Array,
        required: true
      },
      index: {
        type: Number,
        required: true
      }
    },
    data() {
      return{
        selected: null,
        allItems: [] // 모든 가능한 옵션
      }
    },
    computed:{
      // filteredItems(){
      //   // 선택된 항목을 제외한 항목만 필터링
      //   return this.allItems.filter(item => !this.selectedItems.includes(item.id))
      // }
   
    },
    created() {
      this.initializeItems();
    },
    methods :  {
      initializeItems(){
        this.allItems = [];
        for(let i=0; i<15; i++){
          this.allItems.push({ id: i + 1, name: `${i + 1}` });
        }
      },
      handleChange() {
        if (this.selectedItems.includes(this.selected)) {
          alert('이 항목은 이미 선택된 항목입니다. 다른 숫자를 선택해 주세요.');
          this.$nextTick(() => {
            this.selected = null;
          }); 
        } else {
          this.$emit('update-selected', this.index, this.selected)
          console.log('Handle change selected value = ',this.selected)
        }
      }
    }
 
    
};




</script>

<style>
    .cell{
        border: 2px solid #000000;
        width: 70px;
        height: 70px;
    }
    .cell:hover{
      border: 2px solid #8b0000;
      cursor: pointer;
    }
    /* .no-arrow-select .v-select__slot {
      padding-right: 0 !important;
    } */
    .no-arrow-select .v-select__append-inner {
      display: none; /* 화살표 아이콘 숨기기 */
    }
    .mdi-menu-down::before {
      content: none;
    }
    /* v-select{
      text-align: center;
    } */
    /* .v-select__selections input{
      flex: none;
    } */
    
</style>