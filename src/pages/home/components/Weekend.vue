<template>
    <div>
        <div class="title">周末去哪儿</div>
        <ul>
            <li class="item" v-for="item of recommenedList" :key='item.id'>
                <div class="item-img-wrapper">
                    <img class="item-img" :src="item.imgUrl" alt="">
                </div>
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name:'HomeWeekend',
    data () {
        return{
            recommenedList:[
                {
                    id:'0001',
                    imgUrl:'http://img1.qunarzz.com/sight/source/1505/f1/ae9d4299b8aaea.jpg_r_640x214_0c555905.jpg',
                    title:"大连圣亚海洋世界",
                    desc:"浪漫大连首站，浪漫的海洋主题公园"
                },{
                    id:'0002',
                    imgUrl:'http://img1.qunarzz.com/sight/source/1505/f1/ae9d4299b8aaea.jpg_r_640x214_0c555905.jpg',
                    title:"大连圣亚海洋世界",
                    desc:"浪漫大连首站，浪漫的海洋主题公园"
                },{
                    id:'0003',
                    imgUrl:'http://img1.qunarzz.com/sight/source/1505/f1/ae9d4299b8aaea.jpg_r_640x214_0c555905.jpg',
                    title:"大连圣亚海洋世界",
                    desc:"浪漫大连首站，浪漫的海洋主题公园"
                }
            ]
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
        /* overflow hidden
        display flex */
        height 4rem
        .item-img-wrapper
            overflow hidden
            height 0
            padding-bottom 33.9%
            background red
            .item-img
                width 100%
        .item-info
            padding .1rem
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
</style>


