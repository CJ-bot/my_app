<template>
    <div class="icons">
        <swiper :options="swiperOption">
            <swiper-slide v-for='(page, index) of pages' :key='index'>
                <!-- 通过v-for来遍历pages来实现图标区分页 -->
                <div class="icon" v-for="item of page" :key="item.id">
                    <!-- 通过v-for来遍历page来实现单页里的图标按顺序排序 -->
                    <div class="icon-img">
                        <img :src="item.imgUrl" class="icon-img-content">
                    </div>
                    <p class="icon-desc">
                        {{item.desc}}
                    </p>
                </div>
            </swiper-slide>
        </swiper>
    </div>
</template>
<script>
export default {
    name:'HomeIcons',
    props:{
        list:Array
    },
    data(){
        return{
            //autoplay自动播放除了有true和false值以外，还可以直接指定轮播的时间间隔 例如autoplay：5000
            swiperOption:{
                autoplay: false
            }
        }
    },
    computed:{
        pages () {
            const pages = []
            this.list.forEach((item,index) =>{
                //index是图标数组的索引，利用索引除以8来计算是否分页
                const page = Math.floor(index/8)
                if(!pages[page]){
                    pages[page]=[]
                }
                pages[page].push(item)
            })
            return pages
        }
    }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';
// .icons >>> .swiper-container
//   height 0
//   padding-bottom 50%
//   background #eee
// .icon
//   position relative
//   overflow hidden
//   float left
//   width 25%
//   height 0
//   padding-bottom 25%
// .icon-img
//   position absolute
//   top 0
//   left 0
//   right 0
//   bottom .44rem
//   box-sizing border-box
//   .icon-img-content
//     display block
//     margin 0 auto
//     height 100%
// .icon-desc
//   position absolute
//   left 0
//   right 0
//   bottom 0
//   height .44rem
//   line-height .44rem
//   text-align center
//   ellipsis()
     .icons >>> .swiper-container
       height 0
       padding-bottom 50%
       background #eee
     .icon
       overflow hidden
       float left
       width 25%
       height 0
       padding-bottom 25%
       position relative
       .icon-img
         position absolute
         top 0
         left 0
         right 0
         bottom .44rem
         box-sizing border-box
         .icon-img-content
           display block
           margin 0 auto
           height 100%
       .icon-desc
         position absolute
         left 0
         right 0
         bottom 0
         height .44rem
         line-height .44rem
         text-align center
         ellipsis()
</style>