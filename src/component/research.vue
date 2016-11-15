<template>
  <div class="demo">
    <span>this is a recently adding number</span>
    <span>{{number}}</span>
    <br>
    <span>this is a one second increase one number:</span>
    <span>{{adds}}</span>
    <button type="button" name="button" @click="add" >点击</button>
  </div>
</template>

<script type="text/javascript">
export default {
  data () {
    return {
      number:0,
      adds:Number(0)
    }
  },
  methods:{
    add:function(){
      this.number++;
    }
  },
  created (){

      console.log(this.number);



  },
  mounted () {
    var that=this;
    setInterval(
      function(){
        that.adds=that.adds+1;
        // console.log(that.adds);
      },
      1000
    )

}

}
</script>

<style>

</style>
