<template>
  <div class="wrapper">
    <swiper :options="swiperOption" v-if="showSwipper"> 
      <swiper-slide v-for="item in list" :key="item.id">
          <img class="swipper-img" :src="item.imgUrl">
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
  export default {
    name: 'HomeSwipper',
    props:{
      list:Array
    },
    data() {
      return {
        swiperOption: {
           pagination: '.swiper-pagination',
           loop:true,
           autoplay:2000
        },
        }
    },
    computed:{
      showSwipper(){
        return this.list.length
      }
    }

  }

</script>

<style lang="stylus" scoped>
.wrapper >>> .swiper-pagination-bullet-active
    background #fff
.wrapper
    overflow hidden
    width 100%
    height 0
    padding-bottom 30%

    .swipper-img 
        width 100%

</style>
