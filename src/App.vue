<template>
  <div id="app">
    <el-contioner>
      <el-header>
        <h1>大纲可视化分析系统<span id="identity">管理员端</span></h1>
      </el-header>
      <el-aside>
        <div class="sidebar-container">
                  <AdminMenu />
        </div>
      </el-aside>
    </el-contioner>
  </div>
</template>


<script>
import AdminMenu from '@/components/AdminMenu'
export default {
  name: 'App',
  components:{
    AdminMenu
  }
};
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
</style>

