<template>
  <el-dialog title="提示" :visible="visible" width="30%">
    <span>这是一段信息</span>
    <span slot="footer" class="dialog-footer">
      <el-button @click="closeDialog">取 消</el-button>
      <el-button type="primary" @click="closeDialog">确 定</el-button>
    </span>
  </el-dialog>
</template>

<script>
export default {
  name: 'BaseDialog',
  data () {
    return {
      // msg: '我是基础组件'
    }
  },
  props: {
    visible: Boolean,
    aaa: {
      type: Boolean,
      default: false
    }
  },
  computed: {
    // newVisible () {
    //   return this.visible
    // }
  },
  created () {
    console.log('子组件执行了')
  },
  methods: {
    closeDialog () {
      this.$emit('update:visible', false)
    }
  }
}
</script>

<style scoped lang="less">
</style>
