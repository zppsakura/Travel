<template>
    <div>
        <div class="banner" @click="bannerClick">
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
        <common-gallary 
        :imgs="imgs"
        v-show="showGallary"
        @close="gallaryClose"
        >
        </common-gallary>
    </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
    name:'DetailBanner',
    data(){
        return{
            imgs:[
                {
                    id:'0001',
                    imgUl:'http://img1.qunarzz.com/sight/p0/1709/76/7691528bc7d7ad3ca3.img.png_r_800x800_56e729ef.png'
                },{
                    id:'0002',
                    imgUl:'http://img1.qunarzz.com/sight/p0/1709/42/426917ba25e5da3ca3.img.png_r_800x800_f7459750.png'
                }
            ],
           showGallary:false 
        }
    },
    methods:{
        bannerClick(){
            this.showGallary = true
        },
        gallaryClose(){
            this.showGallary = false
        }
    },
    components:{
        CommonGallary
    }
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


