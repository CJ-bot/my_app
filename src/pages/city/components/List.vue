<template>
    <div class="list" ref="wrapper">
        <div>
        <div class="area">
            <div class="title border-topbottom">当前城市</div>
            <div class="button-list">
                <div class="button-wrapper">
                    <div class="button">北京</div>
                    <div class="button">{{this.$store.state.city}}</div>
                </div>
            </div>
        </div>
        <div class="area">
            <div class="title border-topbottom">热门城市</div>
            <div class="button-list">
                <!-- 通过item循环遍历传入的数据hot -->
                <div class="button-wrapper" v-for="item of hot" :key="item.id">
                    <div class="button">{{item.name}}</div>
                </div>
            </div>
        </div>
        <div class="area" v-for="(item, key) of cities" :key="key" :ref="key">
            <div class="title border-topbottom">{{key}}</div>
            <div class="item-list">
                <div class="item border-bottom" v-for="innerItem of item" :key="innerItem.id">
                    {{innerItem.name}}
                </div>
            </div>
        </div>
        </div>
    </div>
</template>

<script>
import Bscroll from 'better-scroll'
// 添加better-scroll
export default {
    name:'CityList',
    //props种制定传入数据的类型
    props:{
        hot:Array,
        cities:Object,
        letter:String
    },
    methods:{
        handleCityClick(city){
            this.$store.dispatch('changeCity',city)
            this.$router.push('/')
        }
    },
    // 添加声明周期函数并调用
    mounted(){
        this.scroll=new Bscroll(this.$refs.wrapper,{click:true})
    },
    //通过watch监听letter的变化，在通过scroll的方法滚动到对应的letter位置
    watch:{
        letter(){
            if(this.letter){
                const element=this.$refs[this.letter][0]
                //console.log(element)
                this.scroll.scrollToElement(element)
            }
        }
    }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.border-topbottom
  &:before
    border-color #cccccc
  &:after
    border-color #cccccc
.border-bottom
  &:after
    border-color #cccccc
// 添加.list类
.list
  position absolute
  overflow hidden
  top 1.58rem
  left 0
  right 0
  bottom 0
  .title
    line-height .44rem
    background #eeeeee
    padding-left .2rem
    color #666
    font-size .26rem
  .button-list
    overflow hidden
    padding-left .1rem .6rem .1rem .1rem
    .button-wrapper
      float left
      width 33.33%
      .button
        text-align center
        margin 0.1rem
        padding 0.1rem 0
        border 0.02rem solid #cccccc
        border-radius 0.08rem
.item-list
  .item
    line-height 0.54rem
    padding-left .2rem
</style>