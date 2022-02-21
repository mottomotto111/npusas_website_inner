<template>
    <div id="choose">
        <el-menu
            class = "menu-admin"
            background-color = "#545c64"
            text-color = '#fff'
            active-text-color = "#ffdo4b"
        >
            <el-menu-item index="首页">
                <i class="el-icon-menu"></i>
                <span slot="title">首页</span>
            </el-menu-item>
            <el-menu-item index="用户管理">
                <i class="el-icon-menu"></i>
                <span slot="title">用户管理</span>
            </el-menu-item>
            <el-menu-item index="文件管理">
                <i class="el-icon-menu"></i>
                <span slot="title">文件管理</span>
            </el-menu-item>
        </el-menu>
    </div>
</template>