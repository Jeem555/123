
<template>
  <div>
    <template v-for="item in treeData">
      <el-submenu
        :index="item._id"  v-if="item.children && item.children.length > 0">
        <template slot="title">
          <span>{{item.menuName}}</span>
        </template>
        <TreeMenu :treeData="item.children"></TreeMenu>
      </el-submenu>
    <el-menu-item v-else :index="item.path"
          :key="item._id"> {{item.menuName}}</el-menu-item>   
    </template>
  </div>
</template>

<script>
export default {
  name: "TreeMenu",
  props:{
    treeData:{
      type:Array,
      default:function(){
        return []
      }
    }
  }
}
</script>

<style scoped>

</style>
