<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <h2>红浪漫 </h2>
  <div>选择一位美女服务</div>
  <div>
  <button
   v-for="(item,index) in girls" 
   v-bind:key="index"
   @click="selectGirlFun(index)"
   >
    {{index}}:{{item}}
  </button>
  <div>您选择了--{{selectGirl}}--为你服务</div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';


export default defineComponent({
  name: 'App',
  setup(){
    const girls = ref(["苍井","三央","爱乃"]);
    const selectGirl = ref("");
    const selectGirlFun = (index: number)=>{
      selectGirl.value = girls.value[index]
    }
    return{girls,selectGirl,selectGirlFun}
  }
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
