<template>
  <el-header>
    <div class="l-content">

      <el-button size="small">
        <el-icon :size="20">
          <Menu />
        </el-icon>
      </el-button>
    </div>
    <div class="r-content">
      <el-dropdown>
        <span class="el-dropdown-link">
          <img class="user" :src="getImgSrc('user')" alt="">
        </span>
        <template #dropdown>
          <el-dropdown-menu>
            <el-dropdown-item>个人中心</el-dropdown-item>
            <el-dropdown-item>退出</el-dropdown-item>

          </el-dropdown-menu>
        </template>
      </el-dropdown>
    </div>
  </el-header>
</template>
<script>
import { requiredNumber } from 'element-plus/es/components/table-v2/src/common';

export default {
  data() {
    return {

    }
  },
  methods: {
    getImgSrc(user) {
      return new URL(`../assets/images/${user}.jpg`, import.meta.url).href;
    }
  }
}
</script>
<style lang="less">
.r-content {
  .user {
    width: 40px;
    height: 40px;
    border-radius: 50%;
  }
}

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
}
</style>