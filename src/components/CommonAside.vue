<template>
     <el-aside width="200px">
          <el-menu class="el-menu-vertical-demo" background-color="#545c64" text-color="#fff"  :collapse="false">
               <el-menu-item :index="item.path" v-for="item in noChildren()" :key="item.path">
                    <el-icon>
                         <component class="icons" :is="item.icon"></component>
                    </el-icon>
                    <span>{{ item.label }}</span>
               </el-menu-item>

               <el-sub-menu :index="item.label" v-for="item of hasChildren()" :key="item.path">
                    <template #title>
                         <el-icon>
                              <component class="icons" :is="item.icon"></component>
                         </el-icon>
                         <span>{{ item.label }}</span>
                    </template>
                    <el-menu-item-group>
                         <el-menu-item :index="subItem.path" v-for="(subItem, subIndex) of item.children"
                              :key="subIndex">
                              <el-icon>
                                   <component class="icons" :is="subItem.icon"></component>
                              </el-icon>~
                              <span>{{ subItem.label }}</span>
                         </el-menu-item>
                    </el-menu-item-group>
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
                         icon: 'user'
                    },

                    {
                         label: '其他',
                         icon: 'location',
                         path: '/other',
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
               return this.list.filter((item) => item.children)
          }
     }
}
</script>