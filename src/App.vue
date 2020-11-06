<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png">
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
  <div><button @click="overAction">点餐完毕</button></div>
  <div>{{overText}}</div>
  </div> -->
  <div>{{nowTime}}</div>
  <div><button @click="getNowTime">显示当前时间</button></div>
</template>

<script lang="ts">
//reactive()
import { 
  defineComponent, ref, reactive, watch,
  toRefs, onBeforeMount, onMounted,
  onBeforeUpdate, onRenderTracked, onRenderTriggered} from 'vue';
import {nowTime,getNowTime} from './hooks/useNowTime';
interface DataProps {
    girls: string[];
    selectGirl: string;
    selectGirlFun: (index: number) => void;
}

export default ({
  name: 'App',
  /*
  setup(){
    console.log("1-开始创建组件---setup()")
    //reactive() 函数接收一个对象作为参数，并返回一个代理对象。
    const data: DataProps = reactive({
girls: ["苍井","三央","爱乃"],
selectGirl: "",
selectGirlFun: (index: number)=>{
   data.selectGirl= data.girls[index]
}
    })


// onBeforeMount(()=>{
//    console.log("2-组件挂在到页面之前执行---onBeforeMount")
// })

// onMounted(()=>{
//   console.log("3-组件挂在到页面之后执行---onMounted")
// })

//  onBeforeUpdate(()=>{
//     console.log("4-组件更新之前执行---onBeforeUpdate")
//  })

//  onUpdate(()=>{
//     console.log("5-组件更新之后执行---onUpdate")
//  })

// onRenderTracked((event)=>{
// console.log("散弹枪状态跟踪钩子函数");
// console.log(event);
// });

// onRenderTriggered((event)=>{
// console.log("狙击枪状态跟踪钩子函数");
// console.log(event);
// })
const refData = toRefs(data)
    // const girls = ref(["苍井","三央","爱乃"]);
    // const selectGirl = ref("");
    // const selectGirlFun = (index: number)=>{
    //   selectGirl.value = girls.value[index]
    // } 注意需要通过.value 属性进行获取值。
//ref 可以把基本的数据结构包装成响应式--即可以直接用到组件中,
//可以理解为把简单类型的数据包装成引用类型，可以有内存地址的。
const overText = ref("红浪漫");
const overAction = ()=>{
   overText.value = "点餐完成|" + overText.value;
  // document.title = overText.value;
}
watch([overText,()=>data.selectGirl], (newValue,oldValue)=>{
  console.log(`new---->${newValue}`);
  console.log(`old---->${oldValue}`);
  document.title = newValue[0];
})
    return{
      // data
    ...refData,
    overText,
    overAction
  }
  
  }
  */
 setup(){

   return {nowTime,getNowTime};
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
