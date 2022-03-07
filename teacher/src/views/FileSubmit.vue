<template>
    <div>
        请上传文档<input type="file">
        <el-input v-model="input" placeholder="请输入课程名称"></el-input>
        <el-button type="primary">提交文档</el-button>
    </div>
</template>

<script>
/* eslint-disable */
    export default{
        name:'FileSubmit'
    }
</script>