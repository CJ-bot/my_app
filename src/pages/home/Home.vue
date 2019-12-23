<template>
      <div>
           <home-header></home-header>
           <home-swiper :list='swiperList'></home-swiper>
           <home-icons :list='iconList'></home-icons>
           <home-hot :list='hotList'></home-hot>
           <home-liked :list='likedList'></home-liked>
           <home-where :list='whereList'></home-where>
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
import axios from 'axios'
export default {
    name: 'Home',
    components:{
        HomeHeader,
        HomeSwiper,
        HomeIcons,
        HomeHot,
        HomeLiked,
        HomeWhere
    },
    data(){
        //使用vuex后不再需要city
        //city:'',
        return{
            swiperList:[],
            iconList:[],
            hotList:[],
            likeLike:[],
            whereLike:[]
        }
    },
    //在methods中定义函数getHomeInfo()
    methods:{
        getHomeInfo(){
            // getHomeInfo中使用axios请求index.json的数据，然后执行getHomeInfoSucc函数
            axios.get('/api/index.json').then(this.getHomeInfoSucc)
            //static目录下的文件可以在地址栏上直接访问，src目录下文件不能直接访问，
            //但是从上线和安全角度考虑我们需要使用代理转发机制将真实的访问目录隐藏替换成api
            //我们可以在config目录下的index.js文件里proxyTable里实现这个
        },
        getHomeInfoSucc(res){
            //统一获取页面模拟的数据
            res=res.data
            if(res.ret && res.data){
                //判断res.ret返回是否真并且数据是否存在
                const data=res.data
                //使用vues后就不需要再传递city数据
                //this.city=data.city
                this.swiperList=data.swiperList
                this.iconList=data.iconList
                this.hotList=data.hotList
                this.likeLike=data.likeLike
                this.whereLike=data.whereLike
            }
        }
    },
    mounted(){
        this.getHomeInfo()
    }
}
</script>

<style scoped>

</style>