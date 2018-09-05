<template>
    <div>
        <home-header></home-header>
        <home-swipper></home-swipper>
        <home-icons></home-icons>
        <home-commened></home-commened>
        <home-weekend></home-weekend>
    </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwipper from './components/Swipper'
import HomeIcons from './components/Icons'
import HomeCommened from './components/Commened'
import HomeWeekend from './components/Weekend'

export default {
    name:'Home',
    components:{
        HomeHeader,
        HomeSwipper,
        HomeIcons,
        HomeCommened,
        HomeWeekend
    }
}
</script>
<style>

</style>

