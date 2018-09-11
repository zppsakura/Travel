<template>
    <div>
        <div class="title">热销推荐</div>
        <ul>
            <router-link 
            tag="li"
            class="item" 
            v-for="item of list" 
            :key='item.id'
            :to="'/detail/' + item.id"
            >
                <div class="item-img-wrapper">
                    <img class="item-img" :src="item.imgUrl" alt="">
                </div>
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                    <button class="item-btn">查看详情</button>
                </div>
            </router-link>
        </ul>
    </div>
</template>

<script>
export default {
    name:'HomeCommened',
    props:{
        list:Array
    },
    data () {
        return{
            
        }
    }
}
</script>

<style lang = "stylus" scoped>
    .title
        line-height .8rem
        background #eee
        margin-top .1rem
        text-indent .2rem 
    .item
        overflow hidden
        display flex
        height 1.9rem
        .item-img
            width 1.7rem
            height 1.7rem
            padding .1rem
        .item-info
            flex 1
            padding .1rem
            min-width 0
            .item-title
                line-height .54rem
                font-size .32rem
                overflow hidden
                white-space nowrap
                text-overflow ellipsis
            .item-desc
                line-height .4rem
                color #ccc
                overflow hidden
                white-space nowrap
                text-overflow ellipsis
            .item-btn
                line-height .44rem
                margin-top .16rem
                background #ff9300
                padding 0 .2rem
                border-radius .1rem
                color #fff
</style>


