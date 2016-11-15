<template>
  <div class="firstDemo">
    <el-row>
    <el-col :span="24"><div class="grid-content bg-purple-dark">实现计数功能</div></el-col>
  </el-row>
 <el-input-number v-model="num1" @change="handleChange" :min="1" :max="10"></el-input-number>
  </div>
</template>

<script type="text/javascript">
export default {
    data() {
      return {
        num1: 1
      };
    },
    methods: {
      handleChange(value) {
        console.log(value);
      }
    }
  };
</script>

<style>

</style>
