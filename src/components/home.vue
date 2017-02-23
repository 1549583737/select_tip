<template>
  <div style="width: 1100px;margin: 40px auto">
    <div class="conditionbox">
      <div class="selectlist">
        <div class="title">地区</div>
        <div class="select-box">
          <seltiplist  v-model="loacl_select">
            <seltipoption v-for=" item in local " :label="item.label" :value="item"></seltipoption>
          </seltiplist>
        </div>
      </div>
      <div class="selectlist">
        <div class="title">薪资要求</div>
        <div class="select-box">
          <seltiplist  v-model="salary_select">
            <seltipoption v-for=" item in salary " :label="item.label" :value="item"></seltipoption>
          </seltiplist>
        </div>
      </div>
      <div class="selectlist">
        <div class="title">福利待遇</div>
        <div class="select-box">
          <seltiplist :multiple="true"  v-model="treatment_select">
            <seltipoption v-for=" item in treatment " :label="item.label" :value="item"></seltipoption>
          </seltiplist>
        </div>
      </div>
      <div class="selectlist">
        <div class="title">已选条件</div>
        <div class="select-box">
          <span class="tip active" v-if="loacl_select">{{loacl_select.label}}</span>
          <span class="tip active" v-if="salary_select">{{salary_select.label}}</span>
          <span class="tip active" v-for="item in treatment_select">{{item.label}}</span>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
  import seltiplist from "./seltiplist.vue";
  import seltipoption from "./seltipoption.vue";

  export default{
    components: {
      seltiplist,
      seltipoption
    },
    data(){
      return{
        loacl_select:"",
        treatment_select:[{
          id:4,
          label:"项目奖金"
        }],
        salary_select:"",
        local:[{
          id:1,
          label:"北京"
        },{
          id:2,
          label:"安徽"
        },{
          id:3,
          label:"上海"
        },{
          id:4,
          label:"广州"
        }],
        treatment:[{
          id:1,
          label:"五险一金"
        },{
          id:2,
          label:"交通补助"
        },{
          id:3,
          label:"带薪年假"
        },{
          id:4,
          label:"项目奖金"
        }],
        salary:[{
          id:1,
          label:"4000以下"
        },{
          id:2,
          label:"4000-6000"
        },{
          id:3,
          label:"6000-8000"
        },{
          id:4,
          label:"8000以上"
        }]

      }
    },
    methods: {}
  }
</script>
<style>
  body, html {
    margin: 0;
    padding: 0;
    font-family: PingFang SC,Hiragino Sans GB,Microsoft Yahei,SimSun,Arial,Helvetica Neue,Helvetica;
    -webkit-font-smoothing: antialiased;
    line-height: 1.42857143;
    color: #666;
    font-size: 14px;
    background: #fdfbfb;
  }

  .conditionbox {
    width: 100%;
    margin-top: 10px;
    background: #fff;
    padding: 20px;
  }

  .selectlist {
    padding-top: 10px;
    padding-bottom: 10px;
  }

  .selectlist .title {
    display: inline-block;
    width: 98px;
    margin-left: 10px;
    font-weight: 700;
    font-size: 15px;
    margin-top: 3px;
  }

  .selectlist .select-box {
    width: 897px;

    position: relative;
    display: inline-block;
  }
  span.tip {
    padding: 3px 6px;
    cursor: pointer;
    border-radius: 3px;
    font-weight: 600;
    margin: 1px 2px;
    color: #465364;
  }
  span.tip:hover{
    color: #fff;
    background: #465364;
  }
  span.tip.active{
    color: #fff;
    background: #465364;
  }
</style>
