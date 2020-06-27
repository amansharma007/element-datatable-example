<template>
  <el-container id="app">
    <el-header>
      <h1>Student Records</h1>
    </el-header>
    <el-main>
      <StudentRecords />
    </el-main>
  </el-container>
</template>

<script>
import StudentRecords from "./components/StudentRecords.vue";

export default {
  name: "App",
  components: {
    StudentRecords
  }
};
</script>

<style>
#app {
  font-family: "Helvetica Neue",Helvetica,"PingFang SC","Hiragino Sans GB","Microsoft YaHei","微软雅黑",Arial,sans-serif;

}
</style>
