<template>
  <div class="layer-wraper">
      <el-container style="height: 100%; border: 1px solid #eee">
        <el-aside width="220px" style="background-color: #0c1855">
            <el-menu :default-openeds="['1']" 
                background-color="#0c1855"
                text-color="#fff">
                <el-menu-item-group>
                    <template slot="title">在线笔试</template>
                    <el-menu-item index="1-1"><i class="el-icon-tickets"></i>笔试列表</el-menu-item>
                    <el-menu-item index="1-2"><i class="el-icon-edit-outline"></i>评卷中心</el-menu-item>
                    <el-menu-item index="1-3"><i class="el-icon-s-operation"></i>笔试题库</el-menu-item>
                    <el-menu-item index="1-4"><i class="el-icon-document"></i>笔试试卷</el-menu-item>
                </el-menu-item-group>
                <el-menu-item-group>
                    <template slot="title">在线面试</template>
                    <el-menu-item index="2-1"><i class="el-icon-tickets"></i>面试列表</el-menu-item>
                    <el-menu-item index="2-2"><i class="el-icon-coin"></i>面试题库</el-menu-item>
                </el-menu-item-group>
                <el-menu-item-group>
                    <template slot="title">团队管理</template>
                    <el-menu-item index="3-1"><i class="el-icon-tickets"></i>团队设置</el-menu-item>
                    <el-menu-item index="3-2"><i class="el-icon-user"></i>成员设置</el-menu-item>
                </el-menu-item-group>
                <el-menu-item-group>
                    <template slot="title">设置</template>
                    <el-menu-item index="4-1"><i class="el-icon-user"></i>个人设置</el-menu-item>
                    <el-menu-item index="4-2"><i class="el-icon-setting"></i>系统设置</el-menu-item>
                </el-menu-item-group>
                <!-- <el-submenu index="1">
                    <template slot="title"><i class="el-icon-message"></i>导航一</template>
                    <el-menu-item-group>
                    <template slot="title">分组一</template>
                    <el-menu-item index="1-1">选项1</el-menu-item>
                    <el-menu-item index="1-2">选项2</el-menu-item>
                    </el-menu-item-group>
                    <el-menu-item-group title="分组2">
                    <el-menu-item index="1-3">选项3</el-menu-item>
                    </el-menu-item-group>
                    <el-submenu index="1-4">
                    <template slot="title">选项4</template>
                    <el-menu-item index="1-4-1">选项4-1</el-menu-item>
                    </el-submenu>
                </el-submenu>
                <el-submenu index="2">
                    <template slot="title"><i class="el-icon-menu"></i>导航二</template>
                    <el-menu-item-group>
                    <template slot="title">分组一</template>
                    <el-menu-item index="2-1">选项1</el-menu-item>
                    <el-menu-item index="2-2">选项2</el-menu-item>
                    </el-menu-item-group>
                    <el-menu-item-group title="分组2">
                    <el-menu-item index="2-3">选项3</el-menu-item>
                    </el-menu-item-group>
                    <el-submenu index="2-4">
                    <template slot="title">选项4</template>
                    <el-menu-item index="2-4-1">选项4-1</el-menu-item>
                    </el-submenu>
                </el-submenu>
                <el-submenu index="3">
                    <template slot="title"><i class="el-icon-setting"></i>导航三</template>
                    <el-menu-item-group>
                    <template slot="title">分组一</template>
                    <el-menu-item index="3-1">选项1</el-menu-item>
                    <el-menu-item index="3-2">选项2</el-menu-item>
                    </el-menu-item-group>
                    <el-menu-item-group title="分组2">
                    <el-menu-item index="3-3">选项3</el-menu-item>
                    </el-menu-item-group>
                    <el-submenu index="3-4">
                    <template slot="title">选项4</template>
                    <el-menu-item index="3-4-1">选项4-1</el-menu-item>
                    </el-submenu>
                </el-submenu> -->
            </el-menu>
        </el-aside>
        
        <el-container>
            <el-header class='header-wraper'>
                <div class="avartar-wraper">
                    <img src="https://fuss10.elemecdn.com/e/5d/4a731a90594a4af544c0c25941171jpeg.jpeg" alt="">
                </div>
                <span>luban</span>
                <el-dropdown>
                    <i class="el-icon-caret-bottom" style="margin-right: 15px"></i>
                    <el-dropdown-menu slot="dropdown">
                    <el-dropdown-item>查看</el-dropdown-item>
                    <el-dropdown-item>新增</el-dropdown-item>
                    <el-dropdown-item>删除</el-dropdown-item>
                    </el-dropdown-menu>
                </el-dropdown>
            </el-header>
            
            <el-main>
              <router-view></router-view>
            </el-main>
        </el-container>
    </el-container>
  </div>
</template>

<script>
  export default {
    data() {
      const item = {
        date: '2016-05-02',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1518 弄'
      };
      return {
        tableData: Array(20).fill(item)
      }
    }
  };
</script>

<style lang='scss' scoped>
.layer-wraper{
    height: 100%;
    .header-wraper{
        display: flex;
        justify-content: flex-end;
        font-size: 12px;
        .avartar-wraper{
            width: 40px;
            height: 40px;
            border-radius: 25px;
            overflow: hidden;
            display: inline-block;
            margin: 10px;
            img{
                width: 100%;
                height: 100%;
                background: rgb(45, 114, 204);
            }
        }
    }

}

</style>
<style lang='scss'>
  .el-header {
    background-color: #ffffff;
    color: #333;
    line-height: 60px;
    border-bottom: 1px solid rgb(233, 233, 233);
  }
  
  .el-aside {
    color: #333;
  }
  .el-menu-item{
      padding: 0px;
  }
  .el-menu-item-group__title{
    color: rgb(202, 202, 202);
}
.el-menu-item, .el-submenu__title{
    height: 40px;
    line-height: 40px;
}
</style>