<template>
  <div class="common-layout">
    <el-container>
      <common-aside></common-aside>
      <el-container class="r-container">
        <common-header />
        <el-main>
          <router-view />

        </el-main>
      </el-container>
    </el-container>
  </div>
</template>


<script>
import CommonHeader from '../components/CommonHead.vue'
import CommonAside from '../components/CommonAside.vue'

export default {
  components: {
    CommonHeader,
    CommonAside
  }
}
</script>

<style lang="less">
.r-container {
  flex-wrap: wrap;
}

.common-layout {
  height: 100%;

  .el-container {
    height: 100%;

    .el-aside {
      height: 100%;
      background: #545c64;
    }
  }
}
</style>