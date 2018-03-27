<template>
  <div class="customer-manager-page">
    <div class="form-list-box">
      <el-form :inline="true" :model="formInline" class="demo-form-inline" size="small">
        <!-- 订单编号 -->
        <el-form-item label="申请单编号：">
          <el-input v-model="formInline.number" placeholder="输入申请单编号" clearable></el-input>
        </el-form-item>
        <!-- 订单状态 -->
        <el-form-item label="申请单状态：">
          <el-select v-model="formInline.status" placeholder="选择申请单状态">
            <el-option label="拒绝" value="refuse"></el-option>
            <el-option label="审批不通过" value="11"></el-option>
            <el-option label="取消" value="22"></el-option>
            <el-option label="未提交" value="33"></el-option>
            <el-option label="已提交" value="44"></el-option>
            <el-option label="资料核对" value="55"></el-option>
            <el-option label="总经理审核" value="66"></el-option>
            <el-option label="风控初审" value="77"></el-option>
            <el-option label="风控终审" value="88"></el-option>
            <el-option label="审核通过" value="99"></el-option>
            <el-option label="待收款" value="19"></el-option>
            <el-option label="已还款" value="11"></el-option>
            <el-option label="还款中" value="12"></el-option>
            <el-option label="欠款中" value="13"></el-option>
            <el-option label="已转租" value="14"></el-option>
            <el-option label="收车中" value="15"></el-option>
            <el-option label="已收车" value="16"></el-option>
            <el-option label="未收车" value="17"></el-option>
            <el-option label="未收回" value="18"></el-option>
            <el-option label="待过户" value="19"></el-option>
            <el-option label="过户中" value="20"></el-option>
            <el-option label="已完成" value="21"></el-option>
          </el-select>
        </el-form-item>
        <!-- 客户名称 -->
        <el-form-item label="客户名称：">
          <el-input v-model="formInline.user" placeholder="请输入客户名称" clearable></el-input>
        </el-form-item>
      </el-form>

      <el-form :inline="true" :model="formInline" class="demo-form-inline" size="small">
        <!-- 车牌号 -->
        <el-form-item label="车牌号：">
          <el-input v-model="formInline.carPlate" placeholder="请输入车牌号" clearable></el-input>
        </el-form-item>
        <!-- 业务类型 -->
        <el-form-item label="业务类型：">
          <el-select v-model="formInline.bussinessType" placeholder="请选择业务类型：">
            <el-option label="分公司直营" value="oneline"></el-option>
            <el-option label="渠道业务" value="channelLine"></el-option>
            <el-option label="电商业务" value="webline"></el-option>
            <el-option label="大客户-陌车" value="mocar"></el-option>
          </el-select>
        </el-form-item>
        <!-- 申请类型 -->
        <el-form-item label="申请类型：">
          <el-select v-model="formInline.applicateType" placeholder="请选择申请类型：">
            <el-option label="企业申请" value="company"></el-option>
            <el-option label="个人申请" value="person"></el-option>
          </el-select>
        </el-form-item>
      </el-form>

      <el-form :inline="true" :model="formInline" class="demo-form-inline" size="small">
        <!-- 车辆类型 -->
        <el-form-item label="车辆类型：">
          <el-select v-model="formInline.carType" placeholder="请选择车辆类型：">
            <el-option label="总部集采" value="headBUy"></el-option>
            <el-option label="当地采购" value="localBuy"></el-option>
            <el-option label="库存车" value="instock"></el-option>
          </el-select>
        </el-form-item>
        <!-- 手机号码 -->
        <el-form-item label="手机号码：">
          <el-input v-model="formInline.mobile" placeholder="请输入手机号码" clearable></el-input>
        </el-form-item>
        <!-- 身份证号码 -->
        <el-form-item label="身份证号码：">
          <el-input v-model="formInline.idNumber" placeholder="请输入身份证号码" clearable></el-input>
        </el-form-item>
      </el-form>

      <el-form :inline="true" :model="formInline" class="demo-form-inline" size="small">
        <!-- 租期 -->
        <el-form-item label="租期：">
          <el-select v-model="formInline.leasePeriod" placeholder="请选择租期：">
            <el-option label="12期" value="12"></el-option>
            <el-option label="24期" value="24"></el-option>
            <el-option label="36期" value="36"></el-option>
          </el-select>
        </el-form-item>
        <!-- 车型 -->
        <el-form-item label="车型：">
          <el-select v-model="formInline.carModel" placeholder="请选择车型：">
            <el-option label="12期11" value="12111"></el-option>
          </el-select>
        </el-form-item>
        <!-- 保证金 -->
        <el-form-item label="保证金：">
          <el-col :span="11">
            <el-input type="number" v-model="formInline.startMargin" placeholder="请输入起始保证金额" clearable></el-input>
          </el-col>
          <el-col class="line" :span="2">-</el-col>
          <el-col :span="11">
            <el-input type="number" v-model="formInline.endMargin" placeholder="请输入结束保证金额" clearable></el-input>
          </el-col>
        </el-form-item>
      </el-form>

      <el-form :inline="true" :model="formInline" class="demo-form-inline" size="small">
        <!--  月供-->
        <el-form-item label="月供：">
          <el-col :span="11">
            <el-input type="number" v-model="formInline.startMonth" placeholder="请输入起始月供金额"></el-input>
          </el-col>
          <el-col class="line" :span="2">-</el-col>
          <el-col :span="11">
            <el-input type="number" v-model="formInline.endMonth" placeholder="请输入结束月供金额"></el-input>
          </el-col>
        </el-form-item>
        <!-- 申请日期 -->
        <el-form-item label="申请日期：">
          <el-col :span="11">
             <el-date-picker type="date" placeholder="选择起始日期" v-model="formInline.date1" style="width: 100%;"></el-date-picker>
          </el-col>
          <el-col class="line" :span="2">-</el-col>
          <el-col :span="11">
             <el-date-picker type="date" placeholder="选择结束日期" v-model="formInline.date2" style="width: 100%;"></el-date-picker>
          </el-col>
        </el-form-item>
      </el-form>
      <div class="operate-btn-box">
        <div class="operate-btn-line">
          <el-col :span="3">
           <el-button type="primary" icon="el-icon-search" size="small" @click="onSearch">搜索</el-button>
          </el-col>
          <el-col :span="3">
            <el-button type="primary" icon="el-icon-plus" size="small" @click="onPlus">新增</el-button>
          </el-col>
          <el-col :span="3">
           <el-button type="primary" icon="el-icon-minus" size="small" @click="onReset">重置</el-button>
          </el-col>
        </div>
      </div>
    </div>
    <!-- 业务列表 -->
    <div class="column-main">
      <div class="header">
        <h4>融资租赁申请表列表</h4>
      </div>
      <div class="customer-list-area">
        <el-table
          :data="tableData"
          border
          stripe
          height="250"
          style="width: 100%">
          <el-table-column
            prop="company"
            label="所属公司"
            width="180">
          </el-table-column>
          <el-table-column
            prop="cardCompany"
            label="上牌分公司"
            width="180">
          </el-table-column>
          <el-table-column
            prop="appNumber"
            label="申请单编号">
          </el-table-column>
          <el-table-column
            prop="contractNum"
            label="合同编号">
          </el-table-column>
          <el-table-column
            prop="bussinessType"
            label="业务类型">
          </el-table-column>
          <el-table-column
            prop="userName"
            label="客户名">
          </el-table-column>
          <el-table-column
            prop="carType"
            label="车型品牌">
          </el-table-column>
          <el-table-column
            prop="appcarModel"
            label="申请车型">
          </el-table-column>
          <el-table-column
            prop="packageType"
            label="套餐车型">
          </el-table-column>
          <el-table-column
            prop="licensePlate"
            label="车牌">
          </el-table-column>
          <el-table-column
            prop="margin"
            label="保证金">
          </el-table-column>
          <el-table-column
            prop="mouth"
            label="月供">
          </el-table-column>
          <el-table-column
            prop="date"
            label="租期">
          </el-table-column>
          <el-table-column
            prop="status"
            label="状态">
          </el-table-column>
          <el-table-column
            prop="appTime"
            label="申请时间">
          </el-table-column>
          <el-table-column
            prop="finance"
            label="是否融资">
          </el-table-column>
          <el-table-column
            prop="mortgage"
            label="是否融资">
          </el-table-column>
          <el-table-column
            prop="operate"
            label="操作">
          </el-table-column>
        </el-table>
      </div>
    </div>
  </div>
</template>

<script>
import local from './local'
const viewName = 'i18nView'

export default {
  name: 'customerManager',
  data() {
    return {
      formInline: {
        user: '',
        status: '',
        number: '',
        carPlate: '',
        bussinessType: '',
        applicateType: '',
        mobile: '',
        idNumber: '',
        carModel: '',
        leasePeriod: '',
        endMargin: '',
        startMargin: '',
        startMonth: '',
        endMonth: '',
        date1: '',
        date2: '',
      },
      tableData: [{
               company: '2016-05-02',
               cardCompany: '王小虎',
               appNumber: '上海市普陀区金沙江路 1518 弄',
               contractNum: 'SQ20180326001003',
               bussinessType: '总部集采',
               userName: '欧阳欧阳',
               carType: '上汽通用',
               appcarModel: '2018款 别克-英朗 1.0T AT 双离合进取型',
               packageType: '1+x B套餐',
               licensePlate: '',
               margin: '2000',
               mouth: '2000',
               date: '36',
               status: '拒绝',
               appTime: '2018-03-26',
               finance: '',
               mortgage: '',
             }, {
              company: '2016-05-02',
              cardCompany: '王小虎',
              appNumber: '上海市普陀区金沙江路 1518 弄',
              contractNum: 'SQ20180326001003',
              bussinessType: '总部集采',
              userName: '欧阳欧阳',
              carType: '上汽通用',
              appcarModel: '2018款 别克-英朗 1.0T AT 双离合进取型',
              packageType: '1+x B套餐',
              licensePlate: '',
              margin: '2000',
              mouth: '2000',
              date: '36',
              status: '拒绝',
              appTime: '2018-03-26',
              finance: '',
              mortgage: '',
             }, {
              company: '2016-05-02',
              cardCompany: '王小虎',
              appNumber: '上海市普陀区金沙江路 1518 弄',
              contractNum: 'SQ20180326001003',
              bussinessType: '总部集采',
              userName: '欧阳欧阳',
              carType: '上汽通用',
              appcarModel: '2018款 别克-英朗 1.0T AT 双离合进取型',
              packageType: '1+x B套餐',
              licensePlate: '',
              margin: '2000',
              mouth: '2000',
              date: '36',
              status: '拒绝',
              appTime: '2018-03-26',
              finance: '',
              mortgage: '',
             }, {
               company: '2016-05-02',
               cardCompany: '王小虎',
               appNumber: '上海市普陀区金沙江路 1518 弄',
               contractNum: 'SQ20180326001003',
               bussinessType: '总部集采',
               userName: '欧阳欧阳',
               carType: '上汽通用',
               appcarModel: '2018款 别克-英朗 1.0T AT 双离合进取型',
               packageType: '1+x B套餐',
               licensePlate: '',
               margin: '2000',
               mouth: '2000',
               date: '36',
               status: '拒绝',
               appTime: '2018-03-26',
               finance: '',
               mortgage: '',
             }]
    }
  },
  created() {
    if (!this.$i18n.getLocaleMessage('en')[viewName]) {
      this.$i18n.mergeLocaleMessage('en', local.en)
      this.$i18n.mergeLocaleMessage('zh', local.zh)
    }
  },
  computed: {
    lang: {
      get() {
        return this.$store.state.app.language
      },
      set(lang) {
        this.$i18n.locale = lang
        this.$store.dispatch('setLanguage', lang)
      }
    }
  },
  methods: {
    onSearch(e) {
      console.log(e);
    },
    onPlus(e) {
      console.log(e);
    },
    onReset(e) {
      console.log(e);
    },
    handleEdit(index,row) {
      console.log(index,row)
    },
    handleDelete(index,row) {
      console.log(index,row)
    }
  }
}
</script>

<style scoped lang="scss">

@import "src/styles/mixin.scss";

.customer-manager-page {
  margin: 16px 12px;
  .form-list-box {
     padding: 30px 12px;
     border: 1px solid #e1e1e1;
    // padding: 30px 20px 15px 20px;
    .line {
      text-align: center;
    }
    .operate-btn-box{
      text-align: center;
      .operate-btn-line {
        @include clearfix;
      }
    }
  }
}
</style>
