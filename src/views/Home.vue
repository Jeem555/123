<template>
  <div class="home">
    <el-container style="height: 100%; border: 1px solid #eee">
      <el-aside width="200px" style="background-color: rgb(238, 241, 246)">

        <el-menu router>
          <TreeMenu :tree-data="treeData"/>
        </el-menu>

      </el-aside>
      <el-container>
        <el-main>
          <router-view></router-view>
        </el-main>
      </el-container>
    </el-container>
  </div>
</template>

<script>
// import treeData from "../mock/index.json";
import TreeMenu from "../components/TreeMenu";

export default {
  name: 'Home',
  components: {
    TreeMenu
  },
  data() {
    return {
      treeData: [{
    _id: "1",
    menuType: "1",
    menuName: "系统管理",
    path: "/system",
    icon: "el-icon-setting",
    children: [
      {
        _id: "2",
        menuType: "1",
        menuName: "用户管理",
        path: "/system/user",
        children: [
          {
            _id: "3",
            menuType: "1",
            menuName: "新增",
            path: "/system/user/add"
          }
        ]
      }
    ]
  }]
    }
  }
}
</script>
<style lang="less">
* {
  margin: 0;
  padding: 0;
}

.home {
  height: 100vh;
}
</style>
