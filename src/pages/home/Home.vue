<template>
      <div>
           <home-header></home-header>
           <home-swiper></home-swiper>
           <home-icons></home-icons>
           <home-hot></home-hot>
           <home-liked></home-liked>
           <home-where></home-where>
      </div>
</template>

<script>
import HomeHeader from './componets/header'
import HomeSwiper from './componets/swiper'
import HomeIcons from './componets/Icons'
import HomeHot from './componets/Hot'
import HomeLiked from './componets/liked'
import HomeWhere from './componets/where'
//添加HomeIcons组件
export default {
    name: 'Home',
    components:{
        HomeHeader,
        HomeSwiper,
        HomeIcons,
        HomeHot,
        HomeLiked,
        HomeWhere
    }
}
</script>

<style scoped>

</style>