<template>
  <div id="app">
    <el-contioner>
      <el-header>
        <h1>大纲可视化分析系统<span id="identity">管理员端</span></h1>
      </el-header>
      <el-aside>
        <div class="sidebar-container">
            <div id="choose">
              <el-menu
                  class = "menu-admin"
                  background-color = "#545c64"
                  text-color = '#fff'
                  active-text-color = "#ffdo4b"
              >
                  <el-menu-item index="首页" v-on:click="viewChange('AdminIndex')" >
                      <i class="el-icon-menu"></i>
                      <span slot="title">首页</span>
                  </el-menu-item>
                  <el-menu-item index="用户管理" v-on:click="viewChange('UserAdmin')">
                      <i class="el-icon-menu"></i>
                      <span slot="title">用户管理</span>
                  </el-menu-item>
                  <el-menu-item index="文件管理">
                      <i class="el-icon-menu" v-on:click="viewChange('FileAdmin')"></i> 
                      <span slot="title">文件管理</span>
                  </el-menu-item>
              </el-menu>
            </div>
        </div>
      </el-aside>
      <el-main>
        <div id="view" :is="currentView"></div>
      </el-main>
    </el-contioner>
  </div>
</template>


<script>

import AdminIndex from './views/AdminIndex'
import UserAdmin from './views/UserAdmin'
import FileAdmin from './views/FileAdmin'

export default {
  name: 'App',
  components:{
    AdminIndex,
    UserAdmin,
    FileAdmin
  },
  data(){
    return{
      activeIndex:'1',
      currentView:'FileAdmin'
    }
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

