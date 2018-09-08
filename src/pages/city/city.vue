<template>
    <div>
        <city-header></city-header>
        <city-input></city-input>
        <city-list></city-list>
        <city-alphabet></city-alphabet>
    </div>
</template>

<script>
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
    } 
}
</script>

<style lang = "stylus" scoped>

</style>


