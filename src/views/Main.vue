<template>
    <div class="common-layout">
      <el-container>
        <common-aside></common-aside>
        <el-container>
          <common-header/>
          <el-main>
            <router-view/>

          </el-main>
        </el-container>
      </el-container>
    </div>
  </template>
  

<script>
import CommonHeader from '../components/CommonHead.vue'
import CommonAside from '../components/CommonAside.vue'

export default {
    components:{
        CommonHeader,
        CommonAside
    }
}
</script>