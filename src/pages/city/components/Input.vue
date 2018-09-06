<template>
    <div class="input">
        <input class="city-input" value='' type="text" placeholder="输入城市名或拼音">
    </div>
</template>

<script>
export default {
    name:'CityInput'
}
</script>

<style lang="stylus" scoped>
    .input
        height .72rem
        background #00bcd4
        padding 0 .1rem
        .city-input
            width 100%
            height .62rem
            box-sizing border-box
            line-height .62rem
            padding 0 .1rem
            text-align center
            color #666
            border-radius .06rem 
            font-size .30rem
            
</style>


