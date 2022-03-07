<template>
    <div>
        课程名称<input type="text">
        <el-button type="primary" icon="el-icon-search">查找大纲</el-button>        
        <el-upload
            class="upload-file"
            action="/doUpload"
            drag multiple :headers="headers" :auto-upload="true"
			 :file-list="fileList" :on-change="handleChange">

            <i class="el-icon-upload"></i>
            <div class="el-upload__text">将文件拖到此处，或<em>点击上传</em></div>
            <!--<div class="el-upload__tip" slot="tip">上传教学大纲</div>-->
            <el-button type="primary" icon="el-icon-plus">上传大纲</el-button> 
        </el-upload>
        <div class="pageGroup">
            <el-button size="small" id="pageprev">上一页</el-button>
            <el-button size="small" id="pageafter">下一页</el-button>
        </div>
        <el-form :model="fileForm" ref="fileForm">
            <el-card class="fileItem" v-for="(item, idx) in fileForm.fileList" :key="idx">
                <el-form-item label="课程名" :prop="`fileList.${idx}.name`">
                    <el-input v-model="item.name" readonly="true"/>
                    <el-button type="primary" icon="el-icon-delete" class="delete"></el-button>
                    <el-button type="primary" id="analyse" >分析</el-button>
                </el-form-item>
            </el-card>
        </el-form>
    </div>
</template>

<script>

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
    }
}
</script>
<style scoped>

    .delete{
        float: right;
        margin-top: 5px;
    }
    .analyse{
        margin-top:5px;
    }

    .pageGroup #pageafter{
        float: right;
    }
</style>