<template>
    <div>
        <home-header :city="city"></home-header>
        <home-swipper :list="swiperList"></home-swipper>
        <home-icons :list="iconList"></home-icons>
        <home-commened :list="recommendList"></home-commened>
        <home-weekend :list="weekendList"></home-weekend>
    </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwipper from './components/Swipper'
import HomeIcons from './components/Icons'
import HomeCommened from './components/Commened'
import HomeWeekend from './components/Weekend'
import axios from 'axios'

export default {
    name:'Home',
    components:{
        HomeHeader,
        HomeSwipper,
        HomeIcons,
        HomeCommened,
        HomeWeekend
    },
    data(){
        return {
            city: '',
            swiperList:[],
            iconList:[],
            recommendList:[],
            weekendList:[]
        }
    },
    methods:{
        getHomeInfo(){
            axios.get('/api/index.json')
                .then(this.getHomeInfoSucc)
        },
        getHomeInfoSucc(res){
            res = res.data
            console.log(res)
            if(res.ret && res.data){
                const data = res.data
                this.city = data.city
                this.swiperList = data.swiperList
                this.iconList = data.iconList
                this.recommendList = data.recommendList
                this.weekendList = data.weekendList
            }
            
            
        }

    },
    mounted(){
        this.getHomeInfo()
    }

}
</script>
<style>

</style>

