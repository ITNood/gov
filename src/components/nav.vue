<template>
  <div>
    <div id="header">
      <div class="container">
          <!--logo-->
        <div class="logo clear">
          <img src="../static/images/logo.png" />
          <div class="right ">
              <div class="header_right flex-center">
                  <el-input v-model="search" class="search"><el-button slot="append" icon="el-icon-search">搜索</el-button></el-input>
                  <a target="_bank" href="https://weibo.com/u/6012681959" class="sina"><img src="../static/images/weibo.png"></a>
                  <div class="wechat relative" @click="chatCode">
                      <img src="../static/images/weixin.png">
                      <img v-if="show" class="wechatcode" src="../static/images/weixincode.jpg">
                  </div>
              </div>
          </div>
        </div>

        <!--nav-->
        <div class="nav flex-center">
            <router-link v-for="(item,index) in items" :key="index" :to="item.url" class="flex-1" active-class="active">{{item.name}}</router-link>
        </div>

      </div>
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  name: "Nav",
  props:['search'],
  data() {
    return {
        show:false,
        items:[
            {url:'/',name:'首页'},
            {url:'/new',name:'新闻'},
            {url:'/technology',name:'科技'},
            {url:'/forestry',name:'林业'},
            {url:'/industry',name:'产业'},
            {url:'/travel',name:'旅游'},
            {url:'/environment',name:'环保'},
            {url:'/culture',name:'文化'},
            {url:'/policy',name:'政策'},
            {url:'/benefit',name:'公益'},
            {url:'/tank',name:'智库'},
            {url:'/approve',name:'认证'},
        ]
    };
  },
  created() {},
  methods: {
      chatCode(){
          this.show=!this.show
      },
  }
};
</script>
<style scoped>
</style>