<template>
  <div class='tab-control'>
    <div v-for="(item,index) in titles" class="tab-control-item" @click="itemClick(index)" >
      <span :class="{active:index===currentIndex}">{{item}}</span>
    </div>
  </div>
</template>

<script>
  export default {
    name:'tabcontrol',
    data(){
      return {
        currentIndex:0
      }
    },
    props:{
      titles:Array
    },
    methods:{
      itemClick(index){
        this.currentIndex = index
      }
    }
  }
</script>

<style>
  .tab-control {
    display:flex;
    text-align: center;
    font-size: 15px;
    height: 40px;
    line-height: 40px;
    background-color: #fff;
  }
  .tab-control .tab-control-item {
     flex:1;
  }
  .active {
    color:var(--color-high-text);
    border-bottom:2px solid var(--color-high-text);
    padding:5px;
  }
</style>