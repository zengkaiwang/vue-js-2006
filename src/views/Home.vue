<template>
  <div class="home">
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
  data: function () {
    return {
      items: [{ message: 'Foo' }, { message: 'Bar' }]
    }
  },
  created: function () {
    console.log(1212)
  },
  beforeRouteEnter (to, from, next) {
    // debugger
    next()
  }
}
</script>
