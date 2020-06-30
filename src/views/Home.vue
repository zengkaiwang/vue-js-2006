<template>
  <div class="home">
    <!-- 强制刷新 -->
    <el-button type="dafault" @click="updateCom">点击更新数组，同时强刷新</el-button>

    <!-- 访问子组件实例或子元素 -->
    <base-input ref="usernameInput"></base-input>

    <!-- sync修饰符实践 -->
    <el-button type="text" @click="showDialog">点击打开 Dialog</el-button>
    <BaseDialog :visible.sync="dialogVisible"></BaseDialog>

    <!-- 自动化局部注册 -->
    <BaseButton></BaseButton>
    <ul id="example-1">
      <li v-for="item in items" :key="item.message">{{ item.message }}</li>
    </ul>
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
  },
  data () {
    return {
      dialogVisible: false,
      items: [{ message: 'Foo' }, { message: 'Bar' }]
    }
  },

  created () {
    console.log('执行了组件created')
    // console.log('父组件的dialogVisible', this.dialogVisible)
  },
  mounted () {
    // console.log('this.$refs.usernameInput', this.$refs.usernameInput)
    this.$refs.usernameInput.focus()
  },
  methods: {
    showDialog () {
      this.dialogVisible = true
    },
    updateCom () {
      this.items.length = 0
      this.$forceUpdate()
    }
  },
  watch: {
    dialogVisible (newQuestion, oldQuestion) {
      console.log('newQuestion', newQuestion, oldQuestion)
    }
  },

  beforeRouteEnter (to, from, next) {
    // debugger
    next()
  }
}
</script>
