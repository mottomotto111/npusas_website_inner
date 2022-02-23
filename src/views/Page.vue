<template>
  <div class="pageGroup">
    <el-button size="small" @click="pervious">上一页</el-button>
    <el-pagination
      @size-change="handleSizeChange"
      @current-change="handleCurrentChange"
      :current-page.sync="current"
      :page-size="pageSize"
      layout="pager"
      :total="total"
      ref="pageGroup">
    </el-pagination>
    <el-button size="small" @click="next">下一页</el-button>
  </div>
</template>
 
<script>
export default {
  name: 'Pages',
  props: {
    currentPage: Number,
    pageSize: Number,
    total: Number,
  },
  data() {
    return {
      current: 1,
    }
  },
  watch: {
    currentPage: {
      handler() {
        this.current = this.currentPage
      },
      deep: true,
    },
  },
  created() {
    this.current = this.currentPage
  },
  methods: {
    handleSizeChange(val) {
      console.log(val)
    },
    handleCurrentChange(val) {
      //console.log(val)
      this.$emit('pageChange', val)
    },
    pervious() {
      this.$refs.pageGroup.prev()
    },
    next() {
      this.$refs.pageGroup.next()
    },
  },
}
</script>
 
<style>
.el-pager li {
  font-size: 12px;
  height: 24px;
  line-height: 18px;
  padding: 0 5px;
  box-sizing: border-box;
}
</style>