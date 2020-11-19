<template>
  <div id="app">
    <h2>我是父组件的data：我现在在父组件里面{{ data }}</h2>
    <HelloWorld
      :data="data"
      @changeData="changeHelloWorld"
      @childzdata="parentFn"
    />
    <h2>我是父组件接收到的子组件的zdata：我现在在父组件里面{{ zdata }}</h2>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
  },
  data() {
    return {
      data: 0,
      zdata: "",
    };
  },
  methods: {
    // 子组件修改父组件的值
    changeHelloWorld(params) {
      this.data += params;
    },
    // 子组件给父组件传值
    parentFn(payload) {
      this.zdata = payload;
    },
  },
};
</script>

<style>

</style>
