<template>
  <div class="demo">

      <button type="button" name="button" v-on:click="reduce">-</button>
      <span>{{num}}</span>
      <button type="button" name="button" v-on:click="add">+</button>
      <br>
      通过计算属性computed计算出的结果<span>{{doneTodosCount}}</span>
      <br>
      通过vuex当中的getters获得的结果<span>{{storeGetter}}</span>
    </div>
</template>
<script type="text/javascript">
import Vue from 'vue'
import Vuex from 'vuex'
Vue.use(Vuex)
const store = new Vuex.Store({
  state: {
    todos: [
      { id: 1, text: '...', done: true },
      { id: 2, text: '...', done: false }
    ]
  },
  getters: {
    doneTodos: state => {
      return state.todos.filter(todo => todo.done)
    }
  }
})
export default {
  data () {
    return {
      num:0,
      storeGetter:store.getters.doneTodos
    }
  },
  computed: {
  doneTodosCount () {
    return store.state.todos.filter(todo => todo.done)
  }
},
  methods:{
  add(){
    this.num++
    // store.commit('increment');
    // console.log(store.state.count);
  },
  reduce(){
    this.num--
    // store.commit('reducement');
    // console.log(store.state.count);
  }
}
}



</script>
<style>

</style>
