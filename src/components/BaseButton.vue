<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: 'BaseButton',
  data: function () {
    return {
      msg: '我是基础组件'
    }
  }
}
</script>

<style scoped lang="less">
</style>
