<template>
  <div>
    <!-- 
      1、首先安装vuex 可以翻墙 npm install vuex --save  不可以用 cnpm install vuex --save
      2、新建一个stroe文件夹 新建一个index.js 
      3、载入 Vue 全局方法和 Vuex方法
      4、main.js引入
      5、vuex管理分为，state，getter,mutations,actions
      import Vue from 'vue';
      import Vuex from 'vuex';
      Vue.use(Vuex);
      const state={ //要设置的全局访问的state对象
          name:"ck",
          change:false
          //要设置的初始属性值
      }
      const getters={ //实时监听state值的变化(最新状态)
          isshow(state){//方法名随意,主要是来承载变化的state的值
          /*    if (state.change) { 
                  return state.name;
              } else {
                  return "ck2";
              }   */
              return state.name;
          }
      }
      const mutations= { //mutattions是一个对象，这个对象里面可以放改变state的初始值的方法
          changename(state,name){ //自定义改变state初始值的方法，这里面的参数除了state之外还可以再传额外的参数(变量或对象);
              state.name = name; //触发该方法 this.$store.commit('changename','chenke') commit("定义的方法名","参数")
          }
      }
      //在 Vuex 中，mutations里面的方法 都是同步事务 两个组件里用执行得到的值，每次都是一样的。
      //好在vuex官方API还提供了一个actions，这个actions也是个对象变量，
      //最大的作用就是里面的Action方法 可以包含任意异步操作，
      //这里面的方法是用来异步触发mutations里面的方法，
      //actions里面自定义的函数接收一个context参数和要变化的形参，context与store实例具有相同的方法和属性，所以它可以执行context.commit(' '),
      const actions = {
          showName(context,msg){
              context.commit("changename",msg) //使用this.$store.dispatch("showName","cc")调用 
          }
      }
      const store = new Vuex.Store({
          state,
          getters,
          mutations,
          actions
      });
      export default store;


      <template>
        <div>
          {{name}}
          <div @click="changeName">
            change
          </div>
        </div>
      </template>

      <script>
      export default {
        data(){
          return {
            name:"",
          }
        },
        created(){
          this.name = this.$store.getters.isshow;
        },
        methods:{
          changeName(){
            this.$store.dispatch("showName","cc");
            this.name = this.$store.getters.isshow;
          }
        }
      }
      </script>

      <style >

      </style>
     -->
  </div>
</template>

<script>
export default {
  
}
</script>

<style>
  
</style>