<template>
  <div id="app">
      <h1>大纲可视化分析系统<span id="identity">教师端</span></h1>
      <div class="sidebar-container">
          <div id="choose">
            <el-menu
                class = "menu-admin"
                background-color = "#545c64"
                text-color = '#fff'
                active-text-color = "#ffdo4b"
            >
                <el-menu-item index="首页"  >
                    <i class="el-icon-menu"></i>
                    <span slot="title">首页</span>
                </el-menu-item>
                <el-menu-item index="管理大纲" v-on:click="viewChange('FileAdmin')">
                    <i class="el-icon-menu"></i>
                    <span slot="title">管理大纲</span>
                </el-menu-item>
            </el-menu>
          </div>
      </div>
      <div :is="currentView" id="view" ></div>
  </div>
</template>

<script>
/* eslint-disable */
import FileAdmin from './views/FileAdmin.vue'

export default {
  name: 'App',
  data(){
    return{
      activeIndex:'1',
      currentView:'FileAdmin'
    }
  },
  components:{
    FileAdmin
  },
  methods:{
    viewChange(item){
      this.currentView = item;
    }
  }
}
</script>

<style>

h1{
    text-align: left;
    color: #0080ff;
    font-family: '楷体';
    font-size: 30px;
    font-weight:bolder;
    margin-top:0px;
}

h1 #identity{
    color:#0060ff;
    font-family: '微软雅黑';
    font-size: 15px;
}

.sidebar-container{
    -webkit-transition: width 0.28s;
    transition: width 0.28s;
    width: 200px !important;
    background-color: #304156;
    height: 100%;
    position: fixed;
    top:50px;
    bottom: 0;
    left: 0;
    z-index: 1001;
    overflow: hidden;
    -webkit-box-shadow: 2px 0 6px rgb(0 21 41 / 35%);
    box-shadow: 2px 0 6px rgb(0 21 41 / 35%);
}

#view{
  width:1000px;
  position: fixed;
  top:50px;
  left: 200px;
}
</style>

