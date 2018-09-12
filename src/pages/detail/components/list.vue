<template>
    <div>
        <div class="list" v-for="(item,index) in list" :key="index">
            <div class="list-item border-bottom">
                <span class="list-item-icon"></span>
                {{item.title}}
            </div>
            <div class="list-children" v-if="item.children">
                <detail-list :list="item.children"></detail-list>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name:'DetailList',
    props:{
        list:Array,
    }
}
</script>

<style lang="stylus" scoped>
.list-item
    line-height .8rem
    font-size .32rem
    color #666
    padding 0 .2rem
    .list-item-icon
        display: inline-block;
        position  relative 
        left .06rem
        top .06rem
        width: .36rem;
        height: .36rem;
        background: url(//s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat;
        margin-right: .1rem;
        background-size: .4rem 3rem;
.list-children
    padding 0 .2rem
    
</style>


