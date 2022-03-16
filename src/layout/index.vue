<template>
  <div class="layout">
    <el-container>
      <el-aside width="200px">
        <Sidebar class="sidebar-container" />
      </el-aside>
      <el-container>
        <el-header>Header</el-header>
        <el-main>
          <AppMain />
        </el-main>
      </el-container>
    </el-container>
  </div>
</template>

<script>
// import { postFetchToken } from "@/api/token";
import { AppMain, Sidebar } from "./components";
export default {
  name: "Layout",
  components: {
    Sidebar,
    AppMain,
  },
  async created() {
    // const params = {
    //   username: "zhangchuang",
    //   password: "123456",
    //   tenantId: "000000",
    // };
    // let res = await postFetchToken(params);
    // console.log(res);
  },
};
</script>

<style lang="scss" scoped>
.el-header {
  line-height: 60px;
  color: #333;
  background-color: #b3c0d1;
}

.el-aside {
  min-height: 100vh;

  .sidebar-container {
    height: 100%;
    background-color: #304156;
  }
}

.el-main {
  color: #333;
  background-color: #e9eef3;
}
</style>
