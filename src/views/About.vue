<template>
  <div class="about">
    <h1>This is an about page</h1>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Home',
  components: {
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
