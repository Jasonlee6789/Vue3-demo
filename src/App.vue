<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <h2>红浪漫 </h2>
  <div>选择美女服务</div>
  <div>
  <button v-for="(item,index) in girls" v-bind:key="index">
    {{index}}:{{item}}
  </button>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';


export default defineComponent({
  name: 'App',
  setup(){
    const girls = ref(["苍井","三央","爱乃"]);
    return{girls,}
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
