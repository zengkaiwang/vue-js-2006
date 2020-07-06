<template>
  <div class="main" v-clickoutside="handleHide">
    <button @click="show = !show">点击显示下拉菜单</button>
    <div class="dropdown" v-show="show">
      <div class="item">
        <a href="#">选项 1</a>
      </div>
      <div class="item">
        <a href="#">选项 2</a>
      </div>
      <div class="item">
        <a href="#">选项 3</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BaseDirective',
  data () {
    return {
      show: false
    }
  },
  props: {
    msg: String
  },
  directives: {
    focus: {
      // 指令的定义
      inserted: function (el) {
        el.focus()
      }
    },
    clickoutside: {
      bind (el, binding) {
        function documentHandler (e) {
          if (el.contains(e.target)) {
            return false
          }

          if (binding.expression) {
            binding.value(e)
          }
        }

        el.__vueMenuHandler__ = documentHandler
        document.addEventListener('click', el.__vueMenuHandler__)
      },
      unbind (el) {
        document.removeEventListener('click', el.__vueMenuHandler__)
        delete el.__vueMenuHandler__
      }
    }
  },
  created () {

  },
  methods: {
    handleHide () {
      this.show = false
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
</style>
