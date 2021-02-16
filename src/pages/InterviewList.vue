<!--面试列表-->
<template>
  <div class="interview-list-wraper">
      <div class="title">面试列表</div>
      <div class="search-wraper">
        <el-form :inline="true" :model="formInline" size="mini" class="form-wraper">
          <el-form-item>
              <el-input
                style="width:200px;"
                placeholder="搜索标题"
                suffix-icon="el-icon-search"
                v-model="title">
              </el-input>
          </el-form-item>
          <el-form-item>
              <el-select v-model="statusValue" placeholder="请选择" style="width:120px;">
                <el-option
                  v-for="item in statusOptions"
                  :key="item.value"
                  :label="item.label"
                  :value="item.value">
                </el-option>
            </el-select>
          </el-form-item>
          <el-form-item>
              <el-select v-model="timeValue" placeholder="请选择" style="width:120px;">
                <el-option
                  v-for="item in timeOptions"
                  :key="item.value"
                  :label="item.label"
                  :value="item.value">
                </el-option>
            </el-select>
          </el-form-item>
          <el-form-item>
            <el-checkbox v-model="justseeme">只看我的面板</el-checkbox>
          </el-form-item>
        </el-form>
        <div class="btn-wraper">
          <el-button type="primary" @click="createDate" size='mini'>创建面试</el-button>
        </div>
      </div>
      <el-table
      :data="tableData.slice((page.pageNum-1)*page.pageSize,page.pageNum*page.pageSize)"
      style="width: 100%"
      :header-cell-style="{'font-weight': 'bold', 'color': '#0e0e0e', }"
      >
      <el-table-column v-for="column in columns" :key="column.prop"
        :prop="column.prop"
        :label="column.label">
      </el-table-column>
      <el-table-column label="操作">
        <template slot-scope="scope">
          <el-button type="text" class="jinru">进入</el-button>|
          <el-dropdown trigger="click" size="small" class="more-wraper">
            <span class="el-dropdown-link">
              更多<i class="el-icon-arrow-down el-icon--right"></i>
            </span>
            <el-dropdown-menu slot="dropdown">
              <el-dropdown-item :key='scope.$index'>删除</el-dropdown-item>
            </el-dropdown-menu>
          </el-dropdown>
        </template>
      </el-table-column>
    </el-table>
    <div class="pagination-wraper">
      <el-pagination
        style="float:right;"
        background
        layout="prev, pager, next"
        :page-size="page.pageSize"
        :current-page="page.pageNum"
        :total="tableData.length"
        :pager-count="4">
      </el-pagination>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return{
      justseeme: false,
      formInline:{},
      statusOptions:[
        {
          value: '全部状态',
          label: '全部状态'
        }, {
          value: '未开始',
          label: '未开始'
        }, {
          value: '面试中',
          label: '面试中'
        }, {
          value: '已结束',
          label: '已结束'
        }
      ],
      title: '',
      statusValue:'',
      timeValue:'',
      timeOptions:[
        {
          value: '全部时间',
          label: '全部时间'
        }, {
          value: '最近一周',
          label: '最近一周'
        }, {
          value: '最近一个月',
          label: '最近一个月'
        }, {
          value: '最近三个月',
          label: '最近三个月'
        }, {
          value: '最近一年',
          label: '最近一年'
        }
      ],
      columns: [
        {
          prop: 'board',
          label: '面试板'
        },
        {
          prop: 'participant',
          label: '参与者'
        },
        {
          prop: 'time',
          label: '面试时间'
        },
        {
          prop: 'language',
          label: '所用语言'
        },
        {
          prop: 'changeCount',
          label: '切屏次数'
        },
        {
          prop: 'status',
          label: '状态'
        },
        {
          prop: 'scores',
          label: '得分'
        }
      ],
      tableData:[],
      page: {
        pageSize: 10,
        pageNum: 1,
      }
    }
  },
  created(){
    this.tableData.push({
      board: '李明明的Java面试',
      participant: '李明明，王小华',
      time: '2020-10-25 20:52',
      language: 'JavaScript',
      changeCount: '3',
      status: '面试中',
      scores: '——'
    })
    this.tableData.push({
      board: '李明明的Java面试',
      participant: '李明明，王小华',
      time: '2020-10-25 20:52',
      language: 'JavaScript',
      changeCount: '3',
      status: '未开始',
      scores: '——'
    })
    for(let i=0; i<147; i++){
      this.tableData.push({
      board: '李明明的Java面试',
      participant: '李明明，王小华',
      time: '2020-10-25 20:52',
      language: 'JavaScript',
      changeCount: '3',
      status: '已结束（52分钟）',
      scores: '83'
    })
    }
  },
  methods:{
    // 创建面板
    createDate(){},
  }
}
</script>

<style lang='scss' scoped>
$mainColor: #193dfc;
.interview-list-wraper{
  padding-bottom: 60px;
  .title{
    font-size: 20px;
    font-weight: bold;
    padding-bottom: 20px;
  }
  .search-wraper{
    position: relative;
    .btn-wraper{
      position: absolute;
      top: 0px;
      right: 10px;
      .el-button{
        background-color: $mainColor;
        height: 35px;
        width: 100px;
      }
    }
    /deep/ .el-input__inner{
          height: 35px;
        }
  }
  .pagination-wraper{
      width: cal(100%-220);
      background: white;
      position: fixed;
      bottom: 0px;
      right: 0px;
      padding: 20px 10px 20px 0px;
      z-index: 100;
      text-align: right;
  }
  .jinru{
    color: #394aa0;
  }
}
.el-dropdown-menu{
  .el-dropdown-menu__item{
    color: #e52222
  }
}
.el-form-item{
  margin-right:30px;
}
::v-deep .el-checkbox {
  .el-checkbox__label {
    
  }

  .el-checkbox__input.is-checked .el-checkbox__inner,
  .el-checkbox__input.is-indeterminate .el-checkbox__inner {
    background-color: $mainColor;
    border-color: $mainColor;
  }

  .el-checkbox__input.is-focus .el-checkbox__inner,
  .el-checkbox__inner:hover {
    border-color: $mainColor;
  }
}
::v-deep {
  .el-pagination.is-background .el-pager li:not(.disabled) {
    background-color: #fff; // 进行修改未选中背景和字体
    // color: #fff;
  }
  .el-pagination.is-background .el-pager li:not(.disabled).active {
    background-color: $mainColor; // 进行修改选中项背景和字体
    color: #fff;
  }
  .el-pagination.is-background .el-pager li:hover {
    color: $mainColor;
  }
}
.el-dropdown-link {
    cursor: pointer;
    color: #394aa0;
  }
  .el-icon-arrow-down {
    font-size: 12px;
  }
</style>