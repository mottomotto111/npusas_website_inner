<template>
    <el-contioner>
        <el-head>
            课程名称<input type="text">
            <el-button type="primary" icon="el-icon-search">查找大纲</el-button>
            <input type="file"><el-button type="primary" icon="el-icon-plus">上传大纲</el-button>
            <Pages :currentPage="currentPage" :total="total" :pageSize="pageSize" @pageChange="pageChange"/>
        </el-head>
        <el-main>
            <el-form :model="fileForm" ref="fileForm">
                <el-card class="fileItem" v-for="(item, idx) in fileForm.fileList" :key="idx">
                    <el-form-item label="课程名" :prop="`fileList.${idx}.name`">
                        <el-input v-model="item.name" />
                        <el-button type="primary" icon="el-icon-delete"></el-button>
                        <el-button type="primary" >分析</el-button>
                    </el-form-item>
                </el-card>
            </el-form>
        </el-main>
    </el-contioner>
</template>

<script>
import Pages from './Page';

var file1 = {
    name:'Tom'
};

var file2 = {
    name:'Jack'
}

export default{
    name:"FileAdmin",
    data(){
        return{
            fileForm:{
                fileList:[file1,file2]
            }
        }
    },
    components:{
        Pages
    }
}
</script>