<template>
    <div class="header">
        <div class="header-left">
            <span class="iconfont back-icon">&#xe624;</span>
        </div>
        <input class="header-input" type="text" placeholder="输入城市/景点/游玩主题"/>
        <router-link to='/city'>
            <div class="header-right">
                {{this.$store.state.city}}
                <span class="iconfont arrow-icon">&#xe6aa;</span>
            </div>
        </router-link>
    </div>
</template>

<script>
export default {
    name:'HomeHeader',
}
</script>
<style lang="stylus" scoped>
@import '../../../assets/styles/varibles.styl'
    .header
        display : flex
        line-height : .95rem
        background : $bgColor
        color #fff
        padding-top .1rem
    .header-left
        width : .64rem
        float : left 
        .back-icon
            text-align center
            font-size .4rem
    .header-input
        flex : 1
        height .7rem
        line-height .7rem
        margin-top : .12rem
        margin-left : .2rem
        background : #fff
        border-radius : .1rem
        text-indent .3rem 
        .search-icon
            padding-left .2rem
    .header-right
        padding 0 .1rem
        min-width : 1.04rem
        font-size .32rem
        float : right 
        text-align : center
        color #fff
        .arrow-icon
            font-size .24rem
            margin-left -.04rem
</style>

