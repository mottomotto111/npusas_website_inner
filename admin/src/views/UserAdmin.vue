<template>
    <div>
        用户名<input type="text">
        <el-button type="primary" icon="el-icon-search">查找用户</el-button>
        <el-button type="primary" icon="el-icon-plus" id="add">增加用户</el-button>
        <div class="pageGroup">
            <el-button size="small" id="pageprev">上一页</el-button>
            <el-button size="small" id="pageafter">下一页</el-button>
        </div>
        <el-form :model="userForm" ref="userForm">
            <el-card class="userItem" v-for="(item, idx) in userForm.userList" :key="idx">
                <el-form-item label="名称" :prop="`userList.${idx}.name`">
                    <el-input v-model="item.name" readonly="true"/>
                    <el-button type="primary" icon="el-icon-delete"></el-button>
                </el-form-item>
            </el-card>
        </el-form>
    </div>
</template>

<script>
var user1 = {
    name:'Tom'
};

var user2 = {
    name:'Jack'
}


export default{
    name:"UserAdmin",
    data(){
        return{
            userForm:{
                userList:[user1,user2]
            }
        }
    }
}

</script>

<style>
    #add{
        float:right;
    }

    .el-container .el-main{

        left:0;
    }
    .pageGroup #pageafter{
        float: right;
    }
</style>
