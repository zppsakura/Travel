<template>
    <div>
        <div class="input">
            <input class="city-input" v-model="keyword" type="text" placeholder="输入城市名或拼音">
        </div>
        <div class="search-content" v-show="keyword" ref="search">
            <ul>
                <li class="search-item border-bottom" 
                    v-for="item of foundList" 
                    :key="item.id" 
                    @click="searchCityClick(item.name)"
                    >
                    {{item.name}}
                </li>
                <li class="search-item border-bottom" v-show="isNotFound">
                    没有找到匹配的数据
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
    name:'CityInput',
    props:{
        cities: Object,
        list: Array
    },
    computed: {
        isNotFound() {
            if (this.foundList === undefined) {
                return true
            }
            return this.foundList.length <= 0
        }
    },
    data(){
        return{
            keyword:'',
            timer:null,
            foundList: []
        }
    },
    methods:{
        searchCityClick(city){
            this.$store.commit('changeCity',city)
            this.$router.push('/')
            this.keyword = city
        }
    },
    mounted(){
        this.foundList = this.list
        this.scroll = new BScroll(this.$refs.search)
    },
    watch:{
        keyword(){
            if(this.timer){
                clearTimeout(this.timer)
            }
            if(!this.keyword){
                this.foundList = []
                return
            }
            
            this.timer=setTimeout(()=>{
                const result = []
                for(let i in this.cities){
                    this.cities[i].forEach(value => {
                        if(value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1){
                            result.push(value)
                        }
                    })
                }
                this.foundList = result
            }, 100)
        }
    }
}
</script>

<style lang="stylus" scoped>
    .border-bottom
        &:before
            border-color #cccccc
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
    .search-content
        z-index 1
        overflow hidden
        position absolute
        top 1.58rem
        left 0
        right 0
        bottom 0
        background #eeeeee
        .search-item
            line-height .58rem
            color #666
            padding-left .2rem
            background #fff
        
            
</style>


