<template>
  <el-row>
    <el-col :span="24">
    <el-menu
    :default-active="activeIndex"
    class="el-menu"
    mode="horizontal"
    @select="handleSelect"
    background-color="#0d0d0d"
    text-color="#fff"
    active-text-color="#ffd04b"
    >
      <el-row>
        <el-col :span="24">
          <span>JYUG</span>
          <el-menu-item index="appHome">Home</el-menu-item>
          <el-menu-item index="appVideos">Videos</el-menu-item>
          <el-menu-item index="appMerchants">Merchants</el-menu-item>
        </el-col>
      </el-row>
    </el-menu>
    </el-col>
  </el-row>
</template>

<script>
import { eventBus } from '../main'

export default {
    data() {
      return {
        activeIndex: '1',
      };
    },
    methods: {
      handleSelect(key, keyPath) {
        eventBus.$emit("menuItemSelected", keyPath[0]);
      }
    }
}
</script>

<style scoped>
  .el-menu-item:hover{
    background-color: rgba(240, 255, 255, 0.13) !important;
  }

  .el-menu {
    box-shadow: 0px 5px rgba(0, 0, 0, 0.048);
  }

  .el-menu-item {
    font-size: 1.2rem;
  }

  span {
    font-size: 1.2rem;
    color: #ffd04b;
    height: 56px;
    line-height: 56px;
    white-space: nowrap;
    display: inline-block;
    position: absolute;
    left: 3%;
  }

</style>