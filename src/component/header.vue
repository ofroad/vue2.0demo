<template>
  <el-menu  default-active="1" class="el-menu-demo" mode="horizontal" >
  <el-menu-item index="1">menu1</el-menu-item>
  <el-submenu index="2">
    <template slot="title">menu2</template>
    <el-menu-item index="2-1">选项1</el-menu-item>
    <el-menu-item index="2-2">选项2</el-menu-item>
    <el-menu-item index="2-3">选项3</el-menu-item>
  </el-submenu>
  <el-menu-item index="3">menu3</el-menu-item>
</el-menu>
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

</style>
