<template>
  <div class="demo">

      <button type="button" name="button" v-on:click="reduce">-10</button>
      <span>{{num}}</span>
      <button type="button" name="button" v-on:click="add">+10</button>
      <br>
      通过计算属性computed计算出的结果<span>{{doneTodosCount}}</span>
      <br>
      通过vuex当中的getters获得的结果<span>{{storeGetter}}</span>
    </div>
</template>
<script type="text/javascript">
import Vue from 'vue'
import Vuex from 'vuex'
import { mapMutations } from 'vuex'
Vue.use(Vuex)
const store = new Vuex.Store({
  state: {
    count:0,
    todos: [
      { id: 1, text: '...', done: true },
      { id: 2, text: '...', done: false },
      { id: 3, text: '...', done: true },
    ]
  },
  getters: {
    doneTodos: state => {
      return state.todos.filter(todo => todo.done)
    }
  },
  mutations:{
    increment(state,n){
      state.count+=n
    },
    decrement(state,n){
      state.count-=n
    }
  },
  actions: {
  incrementAsync ({ commit },n) {
return new Promise((resolve,reject)=>{
      setTimeout(() => {
        commit('increment',n)
        console.log(store.state.count);
        resolve()
      }, 1000)
    })
  },
  decrementAsync({dispatch,commit},n){
    return dispatch('incrementAsync',100).then(()=>{
    setTimeout(()=>{commit('decrement',n)
  console.log(store.state.count)},1000)
    })
  }
}
})
export default {
  data () {
    return {
      // num:store.state.count,
      storeGetter:store.getters.doneTodos
    }
  },
  computed: {
    num(){
      return store.state.count
    },
  doneTodosCount () {
    return store.state.todos.filter(todo => todo.done)
  }
},
  methods:{
  add(){
    // this.num++
    // store.commit('increment',10);
    store.dispatch('incrementAsync',100)
    // console.log(store.state.count);
  },
  reduce(){
    // this.num--
    // store.commit('decrement',10);
      store.dispatch('decrementAsync',10)
    // console.log(store.state.count);
  }
}
}



</script>
<style>

</style>
