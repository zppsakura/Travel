<template>
    <div class="container" @click="gallaryClick">
        <div class="wrapper">
            <swiper :options="swiperOption">
                <swiper-slide v-for="item in imgs" :key="item.id">
                    <img class="gallary-img" :src="item.imgUl" width="350px" height="350px">
                </swiper-slide>
                <div class="swiper-pagination" slot="pagination"></div>
            </swiper>
        </div>
    </div>
</template>

<script>
    export default {
        name: "CommonGallary",
        props:{
            imgs:Array
        },
        data(){
            return{
                swiperOption:{
                    pagination:'.swiper-pagination',
                    paginationType:'fraction',
                    observer:true,
                    observeParents:true,
                    loop:true,
                    autoplay:false
                }
            }
        },
        methods:{
            gallaryClick(){
                this.$emit('close')
            }
        }
    };
</script>

<style lang="stylus" scoped>
.container >>> .swiper-container
    overflow inherit 
.container
    z-index 1
    display flex
    flex-direction column
    justify-content center
    position fixed
    top 0
    left 0
    right 0
    bottom 0
    background #000
    .gallary-img
        width 100%
    .swiper-pagination
        color #fff
        bottom  -1rem

</style>