<template>
    <div>
        <router-link tag="div" to="/" class="header-abc" v-show="showAbs">
            <span class="iconfont home-back-icon">&#xe624;</span>
        </router-link>
        <router-link tag="div" to="/" class="header-fixed" v-show="!showAbs">
            <span class="iconfont back-fixed-home">&#xe624;</span>
            <div class="header-txt">景点详情</div> 
        </router-link>
    </div>
</template>

<script>
export default {
    name:'DetailHeader',
    data(){
        return{
            showAbs:true
        }
    },
    methods:{
        handleScroll(){
            const top = document.documentElement.scrollTop
            if(top > 60){
                this.showAbs = false
            }else{
                this.showAbs = true
            }
        }
    },
    activated(){
        window.addEventListener('scroll',this.handleScroll)
    }
}
</script>

<style lang="stylus" scoped>
    .header-abc
        z-index 1
        position absolute
        top .2rem
        left .2rem
        width .8rem
        height .8rem
        line-height .8rem
        background rgba(0,0,0,.8)
        border-radius .4rem
        text-align center
        .home-back-icon
            color #ffffff
            font-size .35rem
            font-weight bold
    .header-fixed
        z-index 1
        position fixed
        top 0
        left 0
        right 0
        bottom 0
        height .86rem
        line-height .86rem
        background #00bcd4
        color #ffffff
        font-size .32rem
        .back-fixed-home
            font-size .4rem
        .header-txt
            position absolute
            top 0
            padding-left 44%
            text-align center
</style>

