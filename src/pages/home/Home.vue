<template>
    <div>
        <home-header></home-header>
        <home-swipper></home-swipper>
        <home-icons></home-icons>
    </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwipper from './components/Swipper'
import HomeIcons from './components/Icons'
export default {
    name:'Home',
    components:{
        HomeHeader,
        HomeSwipper,
        HomeIcons
    }
}
</script>
<style>

</style>

