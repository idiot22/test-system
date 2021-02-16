<template>
  <div class="layer-wraper">
      <el-container style="height: 100%; border: 1px solid #eee">
        <el-aside width="200px" style="background-color: #0c1855;">
            <div>
                <div class="logo">LOGO</div>
                <div class="teamSelect">
                    <el-select v-model="curTeam" placeholder="请选择" size="small" popper-class='teamoption'>
                        <el-option
                        v-for="item in teams"
                        :key="item.value"
                        :label="item.label"
                        :value="item.value">
                        </el-option>
                    </el-select>
                </div>
            </div>
            <el-menu :default-openeds="['1']" 
                router
                :default-active="'/interview-list'"
                background-color="#0c1855"
                text-color="#d4d6e1">
                <el-menu-item-group>
                    <template slot="title">在线笔试</template>
                    <el-menu-item index="1-1"><i class="el-icon-tickets" style="color: #d4d6e1"></i>笔试列表</el-menu-item>
                    <el-menu-item index="1-2"><i class="el-icon-edit-outline" style="color: #d4d6e1"></i>评卷中心</el-menu-item>
                    <el-menu-item index="1-3"><i class="el-icon-s-operation" style="color: #d4d6e1"></i>笔试题库</el-menu-item>
                    <el-menu-item index="1-4"><i class="el-icon-document" style="color: #d4d6e1"></i>笔试试卷</el-menu-item>
                </el-menu-item-group>
                <el-menu-item-group>
                    <template slot="title">在线面试</template>
                    <el-menu-item index="interview-list"><i class="el-icon-tickets" style="color: #d4d6e1"></i>面试列表</el-menu-item>
                    <el-menu-item index="2-2"><i class="el-icon-coin" style="color: #d4d6e1"></i>面试题库</el-menu-item>
                </el-menu-item-group>
                <el-menu-item-group>
                    <template slot="title">团队管理</template>
                    <el-menu-item index="3-1"><i class="el-icon-s-help" style="color: #d4d6e1"></i>团队设置</el-menu-item>
                    <el-menu-item index="3-2"><i class="el-icon-s-custom" style="color: #d4d6e1"></i>成员设置</el-menu-item>
                </el-menu-item-group>
                <el-menu-item-group>
                    <template slot="title">设置</template>
                    <el-menu-item index="4-1"><i class="el-icon-user" style="color: #d4d6e1"></i>个人设置</el-menu-item>
                    <el-menu-item index="4-2"><i class="el-icon-setting" style="color: #d4d6e1"></i>系统设置</el-menu-item>
                </el-menu-item-group>
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
        return {
            teams: [
                {
                    value: '张小明的团队',
                    label: '张小明的团队'
                }
            ],
            curTeam: '张小明的团队'
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
      ::webkit-scrollbar {
            display: none;
    }
  .el-menu-item{
      padding: 0px;
      font-size:14px;
      color: #989db6;
  }
  .el-menu-item-group__title{
    color: rgb(202, 202, 202);
}
.el-menu-item, .el-submenu__title{
    height: 40px;
    line-height: 40px;
}
.logo {
    width: 140px;
    background-color: #e7e8ee;
    height:30px;
    border-radius: 2px;
    margin: 20px 30px;
    text-align: center;
    line-height: 30px;
    color: #30419b;
    font-size: 12px;
}
.teamSelect{
    margin: 20px 30px;
    font-size: 12px;
}
.teamoption .el-select-dropdown__item{
    font-size: 12px;
}
.teamSelect .el-select .el-input__inner{
    background-color: #0c1855;
    font-size: 12px;
    color: #d4d6e1;
    border: 1px solid #333d70;
}
</style>