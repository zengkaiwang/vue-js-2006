<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  created: function () {
    // var obj = new window.WxLogin({
    //   self_redirect: false,
    //   id: 'login_container',
    //   appid: '11111111111',
    //   scope: 'snsapi_login',
    //   redirect_uri: 'http://bd.hcity.com/callBack',
    //   state: 'A123DC35165464',
    //   style: 'black'
    // })
  },

  beforeRouteEnter (to, from, next) {
    next()
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
