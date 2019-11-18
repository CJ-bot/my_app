<template>
    <div class="icons">
        <!--icons是最外层-->
        <div class="icon">
            <div class="icon-img">
                <img src="http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png" alt="" class="icon-img-content">
            </div>
            <p class="icons-desc">景点门票</p>
        </div>
        <!--icon层代表一个图标层-->
        <div class="icon">
            <div class="icon-img">
                <img src="http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png" alt="" class="icon-img-content">
            </div>
            <p class="icons-desc">一日游</p>
        </div>
        <div class="icon">
            <div class="icon-img">
                <img src="http://img1.qunarzz.com/piao/fusion/1803/f5/a963333e1fa802.png" alt="" class="icon-img-content">
            </div>
            <p class="icons-desc">当地好玩</p>
        </div>
        <div class="icon">
            <div class="icon-img">
                <img src="http://img1.qunarzz.com/piao/fusion/1803/ee/5114069893722102.png" alt="" class="icon-img-content">
            </div>
            <p class="icons-desc">游山玩水</p>
        </div>
        <div class="icon">
            <div class="icon-img">
                <img src="http://img1.qunarzz.com/piao/fusion/1803/80/416c6ab3368d1f02.png" alt="" class="icon-img-content">
            </div>
            <p class="icons-desc">全部玩乐</p>
        </div>
    </div>
</template>
<script>
export default {
    name:'HomeIcons'
}
</script>

<style lang="stylus" scoped>
.icons
  overflow hidden
  height 0
  padding-bottom 50%
  background #eee

  .icon
    position relative
    overflow hidden
    float left
    width 25%
    height 0
    padding-bottom 25%
    
    .icon-img
      position absolute
      top .3rem
      left 0
      right 0
      bottom .44rem
      box-sizing border-box
      .icon-img-content
        display block
        margin 0 auto
        height 80%
    .icons-desc
      position absolute
      left 0 
      right 0
      bottom .8rem
      height .44rem
      font-size .2rem
      text-align center
</style>