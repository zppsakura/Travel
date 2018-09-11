<template>
    <div>
        <city-header></city-header>
        <city-input :cities="cities"></city-input>
        <city-list :cities="cities" :hot="hotCities"></city-list>
        <city-alphabet :cities="cities"></city-alphabet>
    </div>
</template>

<script>
import axios from 'axios'
import CityHeader from './components/Header'
import CityInput from './components/Input'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'
export default {
    name:'City',
    components:{
        CityHeader,
        CityInput,
        CityList,
        CityAlphabet
    } ,
    data(){
        return{
            cities:{},
            hotCities:[]
        }
    },
    methods:{
        getCityInfo(){
            axios.get('/api/city.json')
            .then(this.getCityInfoSucc)
        },
        getCityInfoSucc(res){
            res = res.data
            console.log(res)
            if(res.ret && res.data){
                const data = res.data
                this.cities = data.cities
                this.hotCities = data.hotCities
            }
        }
    },
    mounted () {
        this.getCityInfo()
    }
}
</script>

<style lang = "stylus" scoped>

</style>


