<template>
    <div class="banner">
        <img class="banner-img" 
        src="//img1.qunarzz.com/sight/p0/201404/23/04b92c99462687fa1ba45c1b5ba4ad77.jpg_600x330_bf9c4904.jpg" alt="">
        <div class="banner-info">
            <div class="title">大连圣亚海洋世界(AAAA景区)</div>
            <div class="icon">
                <span class="iconfont arrow-icon">&#xe648;</span>
                39
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name:'DetailBanner'
}
</script>

<style lang="stylus" scoped> 
    .banner
        z-index 1
        position relative
        overflow hidden
        width 100%
        height 0
        padding-bottom 55%
        .banner-img
            width 100%
        .banner-info
            display flex
            position absolute
            left 0
            right 0
            bottom 0
            line-height .6rem 
            color #fff  
            background-image linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,0.8))
            .title
                flex 1
                font-size .32rem
                padding 0 .2rem
            .icon
                margin-top .14rem
                padding 0 .4rem
                height .32rem
                line-height .32rem
                border-radius .2rem
                background rgba(0,0,0,.8)
                font-size .24rem
                .iconfont
                    font-size .24rem

</style>


