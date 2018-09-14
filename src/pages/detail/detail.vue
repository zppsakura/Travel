<template>
    <div>
        <detail-banner :sightName="sightName" :bannerImg="bannerImg" :gallaryImgs="gallaryImgs"></detail-banner>
        <detail-header></detail-header>
        <div class="box">
            <detail-list :categoryList="categoryList"></detail-list>
        </div>
    </div>
</template>

<script>
import DetailBanner from "./components/banner";
import DetailHeader from "./components/header";
import DetailList from "./components/list";
import axios from 'axios';
export default {
  name: "Detail",
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  },
  data() {
    return {
        sightName:'',
        bannerImg:'',
        gallaryImgs:[],
        categoryList:[]
    }
  },
  methods:{
      getDetailInfo(){
          axios.get('/api/detail.json',{
              params:{
                  id:this.$route.params.id
              }
          }).then(this.handleDetailSucc)
      },
      handleDetailSucc(res){
          res = res.data
          if(res.ret && res.data){
              const data = res.data
              this.sightName = data.sightName
              this.bannerImg = data.bannerImg
              this.gallaryImgs = data.gallaryImgs
              this.categoryList = data.categoryList
          }
      }
  },
  mounted(){
      this.getDetailInfo()
  }

};
</script>

<style lang="stylus" scoped>
.box {
    height: 50rem;
}
</style>


