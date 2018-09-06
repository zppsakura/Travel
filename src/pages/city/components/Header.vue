<template>
    <div class="header">
        城市选择
        <router-link to="/">
            <span class="iconfont back-home">&#xe624;</span>
        </router-link>
    </div>
</template>

<script>
export default {
    name:'CityHeader'
}
</script>

<style lang = "stylus" scoped>

.header
    position relative
    overflow hidden
    height .86rem
    line-height .86rem
    text-align center
    background #00bcd4
    color #ffffff
    font-size .32rem
    .back-home
        position absolute
        top 0
        left 0
        font-size .4rem
        color #fff
</style>


