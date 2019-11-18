<template>
      <div>
           <home-header></home-header>
           <home-swiper></home-swiper>
           <home-icons></home-icons>
      </div>
</template>

<script>
import HomeHeader from './componets/header'
import HomeSwiper from './componets/swiper'
import HomeIcons from './componets/Icons'
//添加HomeIcons组件
export default {
    name: 'Home',
    components:{
        HomeHeader,
        HomeSwiper,
        HomeIcons
    }
}
</script>

<style scoped>

</style>