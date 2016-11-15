<template>
  <div class="body">
    <headers></headers>
    <div class="container">
      <div class="list">
          <list></list>
      </div>
      <div class="content">
          <router-view class="view"></router-view>
      </div>
    <!-- <firstcomponent></firstcomponent>
    <research></research> -->

    </div>
  </div>
</template>

<script>
// import firstcomponent from './component/firstcomponent.vue'
// import secondcomponent from './component/secondcomponent.vue'
// import research from './component/research.vue'
import list from './component/list.vue'
import headers from './component/header.vue'
// import drag from './component/drag.vue'
export default {
  data () {
    return {
      msg: 'Hello Vue!'
    }
  },
  components: { list,headers }
}


</script>

<style>
body {
  font-family: Helvetica, sans-serif;

}
.container{
  display: flex;
  /*justify-content:space-around;*/
}
.list{
  width: 200px;
  height: 100%;
  border-right: 1px solid black;
}
.content{
  width: 60%;

  margin-left: 20px;
  margin: auto;
}

</style>
