<template>
  <div class="home">
    <el-button type="text" @click="showDialog">点击打开 Dialog</el-button>
    <BaseDialog :visible.sync="dialogVisible"></BaseDialog>
    <BaseButton></BaseButton>
    <img alt="Vue logo" src="../assets/logo.png" />
    <ul id="example-1">
      <li v-for="item in items" :key="item.message">{{ item.message }}</li>
    </ul>
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
// import BaseButton from '@/components/BaseButton.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
    // BaseButton
  },
  data () {
    return {
      dialogVisible: false,
      items: [{ message: 'Foo' }, { message: 'Bar' }]
    }
  },

  created () {
    console.log('父组件的dialogVisible', this.dialogVisible)
  },
  methods: {
    showDialog () {
      this.dialogVisible = true
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
