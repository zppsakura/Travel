<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <swiper-slide v-for="item in swiperlist" :key="item.id">
          <img class="swipper-img" :src="item.imgUrl">
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
  export default {
    name: 'HomeSwipper',
    data() {
      return {
        swiperOption: {
           pagination: '.swiper-pagination',
           loop:true
        },
        swiperlist:[
            {
                id:'0001',
                imgUrl:'https://imgs.qunarzz.com/p/tts0/201405/15/c1332a3d64a5a7a7c8d65eac.jpg_304x201_46215db0.jpg'
            },{
                id:'0002',
                imgUrl:'https://imgs.qunarzz.com/p/tts0/1801/78/b9e250be82959302.jpg_304x201_be595872.jpg'
            },{
                id:'0003',
                imgUrl:'https://imgs.qunarzz.com/p/tts8/1803/95/ced996e83aa6a202.jpg_304x201_b8234d87.jpg'
            }
        ]
      }
    }
  }

</script>

<style lang="stylus" scoped>
.wrapper >>> .swiper-pagination-bullet-active
    background red
.wrapper
    overflow hidden
    width 100%
    height 0
    padding-bottom 40%
    .swipper-img 
        width 100%

</style>
