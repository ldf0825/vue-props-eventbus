<template>
  <div id="app">
    <h1>app.vue</h1>
    <!-- titleChange是注册的事件名，相当于一个click -->
    <app-Header :title="title" @titleChange="updateTitle" />
    <Users :users="users" />
    <Users :users="users" />

    <app-Footer :title="title" />
  </div>
</template>

<script>
//组件内嵌套组件
import Users from "./components/Users.vue";
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";

/*  
    传值 和 传址
    eventbus  子组件向父组件传值

*/
export default {
  name: "app",
  data() {
    return {
      users: [
        { name: "佩奇", position: "小猪家", show: false },
        { name: "苏西", position: "小猪家", show: false },
        { name: "丹尼", position: "小猪家", show: false },
        { name: "苏一", position: "小猪家", show: false }
      ],
      title: { name: "这是传值" }
    };
  },
  components: {
    //"mr-Users": Users
    Users,
    "app-Header": Header,
    "app-Footer": Footer
  },
  methods: {
    updateTitle(name) {
      this.title.name = name;
    }
  }
};
</script>

<style>
h1 {
  color: greenyellow;
}
</style>
