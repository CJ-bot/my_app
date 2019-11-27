<template>
    <div>
        <div class="title">
            <span class="title-content">周末去哪儿</span>
        </div>
        <div class="wrapper" v-for="item of whereList" :key='item.id'>
            <div class="where-img">
                <img :src="item.imgUrl" alt="" class="where-img-content">
            </div>
            <p class="biaoti">{{item.title}}</p>
            <p class="desc">{{item.desc}}</p>
        </div>
    </div>
</template>

<script>
export default {
    name:'HomeWhere',
    data(){
        return{
            whereList:[{
                id:'001',
                imgUrl:'http://img1.qunarzz.com/sight/source/1711/2b/d4ebbd8337f1ac.jpg_r_640x214_2d4332c1.jpg',
                title:'湖南泡汤圣地',
                desc:'山谷幽深，泉水潺潺，宜然的自然风光，怡人的田园景...'
            },{
                id:'002',
                imgUrl:'http://img1.qunarzz.com/sight/source/1509/3a/e163a8e32517d9.jpg_r_640x214_4fd882d3.jpg',
                title:'边城秋色',
                desc:'不得不看的边城秋日之美'
            },{
                id:'003',
                imgUrl:'http://img1.qunarzz.com/sight/source/1811/88/8d3b492ebf0b16.jpg_r_640x214_7b3a281d.jpg',
                title:'邂逅凤凰城',
                desc:'凤凰古城，一个古老而神秘的地方，风景秀丽，历史悠久...'
            },{
                id:'004',
                imgUrl:'http://img1.qunarzz.com/sight/source/1811/b4/71c01c98139cf.jpg_r_640x214_30bac495.jpg',
                title:'亲身体验人间仙境',
                desc:'天桥天地，绝壁高崖之间的高台，台下深不见底的山涧...'
            },{
                id:'005',
                imgUrl:'http://img1.qunarzz.com/sight/source/1812/1e/131ba1bc67be3e.jpg_r_640x214_edd2705d.jpg',
                title:'株洲必打卡',
                desc:'亲身体验株洲当地人最爱的去处'
            }]
        }
    }
}  
</script>

<style lang="stylus" scoped>
.title
  background #eeeeee
  padding .2rem
  .title-content
    height 0.44rem
    color black 
    font-size .32rem
    line-height 0.44rem
.wrapper
  padding-bottom 4%
  .where-img
    overflow hidden
    height 50%
    margin-top -.2rem
    .where-img-content
      width 100%
  .biaoti
    padding-left .2rem
    font-size .28rem
    margin-top .12rem
    line-height .32rem
  .desc
    padding-left .2rem
    font-size .24rem
    margin-top .12rem
    line-height .32rem
    color #777
</style>