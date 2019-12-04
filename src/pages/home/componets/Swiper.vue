<template>
    <div class="wrapper">
        <swiper :options="swiperOption" v-if="list.length">
            <!--slides-->
            <swiper-slide v-for="item of list" :key="item.id">  
                <img class="swiper-img" :src='item.imgUrl' >
            </swiper-slide>
           
            <!--Optional controls-->
            <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
    </div>
</template>
<script>
export default {
    name:'HomeSwiper',
    // 指定props里接收list是数组
    props:{
        list:Array
    },
    data(){
        return{
            swiperOption:{
                pagination:'.swiper-pagination',
                //添加pagination选项并赋值.swiper-pagination来实现轮播图上圆点选项
                loop:true
                //添加loop选项来实现轮播图的循环
            }
        }
    }
}
</script>
<style lang='stylus' scoped>
.wrapper >>> .swiper-pagination-bullet-active
  background #ffffff
  //实现.wrapper对.swiper-pagination-bullet-active的样式穿透
.wrapper
  overflow hidden
  width 100%
  height 0
  padding-bottom 26.66%
  //.wrapper实现按比例站位
.swiper-img
  width 100%
</style>