<template>
  <div class="demo">
    <el-menu  class="el-menu-vertical-demo"  theme="dark">
      <el-menu-item index="1"><router-link to="/first" style="color:#58B7FF;">list-one</router-link></el-menu-item>
      <el-menu-item index="2"><router-link to="/second" style="color:#58B7FF;">list-two</router-link></el-menu-item>
      <el-menu-item index="2"><router-link to="/third" style="color:#58B7FF;">list-three</router-link></el-menu-item>
      <el-menu-item index="2"><router-link to="/forth" style="color:#58B7FF;">list-four</router-link></el-menu-item>
    </el-menu>
  </el-col>
  <el-col :span="8">
  </div>
</template>
<script type="text/javascript">
export default {
  data () {
    return {
    }
  }
}
</script>
<style>
.el-menu-item>a{
  display: block;
width: 100%;
height: 100%;
}
el-menu-item a:hover, a:visited, a:link, a:active {
text-decoration:none;
color: #58B7FF;
}
a:hover{
  color: #13CE66;
}
el-menu-item a:hover，a:visited{
  color: #13CE66;
}
</style>
