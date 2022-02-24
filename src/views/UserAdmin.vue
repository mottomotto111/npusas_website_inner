<template>
    <el-contioner>
        <el-head>
            用户名<input type="text">
            <el-button type="primary" icon="el-icon-search">查找用户</el-button>
            <el-button type="primary" icon="el-icon-plus" id="add">增加用户</el-button>
            <Pages :currentPage="currentPage" :total="total" :pageSize="pageSize" @pageChange="pageChange"/>
        </el-head>
        <el-main>
            <el-form :model="userForm" ref="userForm">
                <el-card class="userItem" v-for="(item, idx) in userForm.userList" :key="idx">
                    <el-form-item label="名称" :prop="`userList.${idx}.name`">
                        <el-input v-model="item.name" />
                        <el-button type="primary" icon="el-icon-delete"></el-button>
                    </el-form-item>
                </el-card>
            </el-form>
        </el-main>
    </el-contioner>
</template>

<script>
var user1 = {
    name:'Tom'
};

var user2 = {
    name:'Jack'
}

import Pages from './Page.vue'

export default{
    name:"UserAdmin",
    data(){
        return{
            userForm:{
                userList:[user1,user2]
            }
        }
    },
    components:{
        Pages
    }
}

</script>

<style>

#add{
    float:right;
}
</style>
