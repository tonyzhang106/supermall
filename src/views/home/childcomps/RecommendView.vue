<template>
  <div class="recommend">
    <div v-for="item in recommends" class="recommend-item">
      <a :href="item.link">
        <img :src="item.image"/>
        <div>{{item.title}}</div>
      </a>
    </div>
  </div>
</template>
<script>
export default {
  name:'recommend',
  props:{
    recommends:Array
  }
}
</script>

<style>
.recommend {
  display:flex;
  font-size:12px;
  padding:10px 0px 20px;
  border-bottom:10px solid #eee;
}
.recommend-item {
  flex:1;
  text-align:center;
}
.recommend-item img {
  width:70px;
  margin-bottom:10px;
}
</style>