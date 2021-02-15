<!--面试列表-->
<template>
  <div class="interview-list-wraper">
      <div class="title">面试列表</div>
      <div class="search-wraper">
        <el-form :inline="true" :model="formInline" size="mini" class="form-wraper">
          <el-form-item >
              <el-input
                placeholder="请选择日期"
                suffix-icon="el-icon-search"
                v-model="input1">
              </el-input>
          </el-form-item>
          <el-form-item>
              <el-select v-model="statusValue" placeholder="请选择">
                <el-option
                  v-for="item in statusOptions"
                  :key="item.value"
                  :label="item.label"
                  :value="item.value">
                </el-option>
            </el-select>
          </el-form-item>
          <el-form-item>
              <el-select v-model="timeValue" placeholder="请选择">
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
          <el-button type="primary" @click="createDate" size='mini'>创建面板</el-button>
        </div>
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
      ]
    }
  },
  methods:{
    // 创建面板
    createDate(){}
  }
}
</script>

<style lang='scss' scoped>
.interview-list-wraper{
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
    }
  }
}
</style>