<template>
  <div class="hello">
    <input ref="input" />
  </div>
</template>

<script>
export default {
  name: 'BaseButton',
  data: function () {
    return {
      msg: '我是基础组件'
    }
  },
  methods: {
    // 用来从父级组件聚焦输入框
    focus: function () {
      this.$refs.input.focus()
    }
  }
}
</script>

<style scoped lang="less">
</style>
