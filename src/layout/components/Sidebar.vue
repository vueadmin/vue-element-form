<template>
  <div class="sidebar">
    <el-scrollbar wrap-class="scrollbar-wrapper">
      <el-menu
        class="scrollbar-wrapper-menu"
        default-active="2"
        background-color="#304156"
        text-color="#bfcbd9"
        @open="handleOpen"
        @close="handleClose"
      >
        <el-menu-item index="Index">
          <i class="el-icon-house"></i>
          <span slot="title">首页</span>
        </el-menu-item>
        <el-menu-item index="Travel">
          <i class="el-icon-position"></i>
          <span slot="title">旅途管理</span>
        </el-menu-item>
        <el-menu-item index="TravelV2">
          <i class="el-icon-position"></i>
          <span slot="title">旅途管理 V2</span>
        </el-menu-item>
        <el-menu-item index="TravelV3">
          <i class="el-icon-position"></i>
          <span slot="title">旅途管理 V3</span>
        </el-menu-item>
      </el-menu>
    </el-scrollbar>
  </div>
</template>

<script>
export default {
  name: "Sidebar",
  methods: {
    handleOpen(key, keyPath) {
      console.log(key, keyPath);
    },
    handleClose(key, keyPath) {
      console.log(key, keyPath);
    },
  },
};
</script>

<style lang="scss" scoped>
.sidebar {
  .scrollbar-wrapper {
    &-menu {
      border-right: 0;
    }
  }
}
</style>
