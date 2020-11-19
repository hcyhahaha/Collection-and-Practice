<template>
  <div class="hello">
    <h2>我是子组件接收到的父组件的data：我现在在子组件里面{{ data }}</h2>
    <button @click="changeFu">修改父组件的值</button>
    <h2>我是子组件的zdata：我现在在子组件里面{{ zdata }}</h2>
    <button @click="ziTofu">子组件给父组件传值</button>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    data: {
      type: Number,
      default: 1,
    },
  },
  data() {
    return {
      zdata: 10,
    };
  },
  methods: {
    changeFu() {
      this.$emit("changeData", 2);
    },
    ziTofu() {
      console.log("childzdata");
      this.$emit("childzdata", this.zdata);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
