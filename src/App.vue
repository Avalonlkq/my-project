<!-- 展示模板 -->
<template>
  <div id="app">
    <img src="./assets/logo.png" />
    <hello></hello>
    <button @click="send">获取联盟信息</button>
    <li v-for="item in items" :key="item.message">
    {{ item.message }}
  </li>
  </div>
</template>
 
<script>
// 导入组件
import Hello from "./components/Hello";

export default {
  name: "app",
  components: {
    Hello,
  },
  data() {
    return {};
  },
  methods: {
    send() {
      this.$http
        .get("/latest/alliances")
        .then((response) => {
          console.log(response);
          alert(response.data);
        })
        .catch((err) => {
          console.log(err);
          alert('请求失败！');
        });
    },
  },
};
</script> 
<!-- 样式代码 -->
<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>