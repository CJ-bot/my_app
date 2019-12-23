<template>
    <div>
        <div class="title">
            <span class="title-content">周末去哪儿</span>
        </div>
        <ul class="item border-bottom" v-for="item of list" :key='item.id'>
            <li class="item-img-wrapper">
                <img :src="item.imgUrl" alt="" class="item-img">
            </li>
            <div class="item-info">
                <p class="item-title">{{item.title}}</p>
                <p class="item-desc">{{item.desc}}</p>
            </div>
        </ul>
    </div>
</template>

<script>
export default {
    name:'HomeWhere',
    name:'HomeIcons',
    props:{
        list:Array
    }
}  
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.title
  line-height .8rem
  background #eeeeee
  text-indent .2rem
.item-img-wrapper
  overflow hidden
  height 0
  padding-bottom 37.09%
  .item-img
    width 100%
.item-info
  padding .1rem
  .item-title
    line-height .54rem
    font-size .32rem
    ellipsis()
  .item-desc
    line-height .4rem
    color #cccccc
    ellipsis()
</style>