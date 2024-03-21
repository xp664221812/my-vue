<template>
     <el-aside width="200px">
          <el-menu class="el-menu-vertical-demo">
               <el-menu-item :index="item.path" v-for="item in noChildren()" :key="item.path">
                    <el-icon><component class="icons" :is="item.icon"></component></el-icon>
                    <span>{{ item.label }}</span>
               </el-menu-item>

               <el-sub-menu index="1">
                    <template #title>
                         <el-icon>
                              <location />
                         </el-icon>
                         <span>Navigator One</span>
                    </template>
                    <el-menu-item-group title="Group One">
                         <el-menu-item index="1-1">item one</el-menu-item>
                         <el-menu-item index="1-2">item two</el-menu-item>
                    </el-menu-item-group>
                    <el-menu-item-group title="Group Two">
                         <el-menu-item index="1-3">item three</el-menu-item>
                    </el-menu-item-group>
                    <el-sub-menu index="1-4">
                         <template #title>item four</template>
                         <el-menu-item index="1-4-1">item one</el-menu-item>
                    </el-sub-menu>
               </el-sub-menu>


          </el-menu>
     </el-aside>
</template>

<script>
export default {
     data() {
          return {
               list: [
                    {
                         path: '/user',
                         name: 'user',
                         label: '用户管理',
                         url: 'UserManager/UserManager',
                         icon:'user'
                    },

                    {
                         label: '其他',
                         icon: 'location',
                         children: [
                              {
                                   path: '/page1',
                                   name: 'page1',
                                   label: '页面1',
                                   icon: 'setting',
                                   url: 'Other/PageOne'
                              },
                              {
                                   path: '/page2',
                                   name: 'page2',
                                   label: '页面2',
                                   icon: 'setting',
                                   url: 'Other/PageTwo'
                              }
                         ]
                    }
               ]
          }
     },
     methods: {
          noChildren() {
               return this.list.filter((item) => !item.children)
          },
          hasChildren() {
               return lisst.filter((item) => item.children)
          }
     }
}
</script>