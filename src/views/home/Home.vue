<template>
  <div id="home">
    <nav-bar class="home-nav">
      <div slot="center">购物街</div>
    </nav-bar>
    <home-swiper :banner="banner" />
  </div>
</template>

<script>
  import NavBar from 'components/common/navbar/NavBar'
  import {getMultiData} from 'network/home'
  import HomeSwiper from './childcomps/HomeSwiper'
  export default {
    name: "Home",
    data(){
      return {
        banner:[]
      }
    },
    created(){
      getMultiData().then(res=>{ 
        this.banner = res.data.banner.list
      })
    },
    components:{
      NavBar,
      HomeSwiper
    }
  }
</script>

<style scoped>
  .home-nav {
    background-color:var(--color-tint);
    color:#fff;
  }
</style>
