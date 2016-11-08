<template>
  <div id="app2">
    <img src="./assets/logo.png">
    <h1>Hello App!</h1>
    <firstcomponent></firstcomponent>
    <research></research>
    <drag></drag> 
    <ul>
        <li><router-link to="/first">点我跳转到第一页</router-link></li>
        <li><router-link to="/second">点我跳转到第二页</router-link></li>
      </ul>
    <router-view class="view"></router-view>
  </div>
</template>

<script>
import firstcomponent from './component/firstcomponent.vue'
import secondcomponent from './component/secondcomponent.vue'
import research from './component/research.vue'
import drag from './component/drag.vue'
export default {
  data () {
    return {
      msg: 'Hello Vue!'
    }
  },
  components: { firstcomponent, secondcomponent,research,drag }
}


</script>

<style>
body {
  font-family: Helvetica, sans-serif;
}
</style>
