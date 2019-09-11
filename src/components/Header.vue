<template>
  <div class="header">
    <h1 @click="changeTitle">{{title.name}}</h1>
    <button @click="changeAppTitle">eventBus</button>
  </div>
</template>

<script>
//子组件传参给父组件 1.子组件触发事件 2.在触发事件中注册事件 3.父组件触发事件 4.父组件实现注册事件方法
export default {
  name: "mr-header",
  props: {
    title: {
      type: Object,
      required: true
    }
  },
  data() {
    return {
      // title: "This is Haader.vue"
    };
  },
  methods: {
    changeTitle() {
      this.title.name = "在header.vue中改变的属性值";
    },
    changeAppTitle() {
      /*@param 1.注册的事件名 2.其他的都是具体传的值 */
      this.$emit("titleChange", "title from Header.vue");
    }
  },
  //生命周期的函数 hooks
  beforeCreate() {
    //几乎不怎么用
    alert("刚刚进入生命周期的钩子函数，在这里可以做一些启动页面的轮播");
  },
  created() {
    //常常用
    alert("在这里我们可以请求数据，请求完数据，可以将数据挂载到data上");
  },
  beforeMount() {
    //不怎么用
    alert("数据还未挂载，准备挂载数据");
  },
  mounted() {
    //常用
    alert("数据已经挂载了，准备渲染页面");
  },
  beforeUpdate() {
    //不怎么用
    alert("接收到数据要更新，但还未更新");
  },
  updated() {
    //偶尔用
    alert("数据更新，并渲染页面");
  }
};
</script>

<style scoped>
.header {
  background: lightcoral;
  padding: 10px;
}
h1 {
  color: black;
  text-align: center;
}
</style>
