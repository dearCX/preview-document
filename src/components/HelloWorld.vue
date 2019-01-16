<template>
  <div class="hello">
    <h2>测试vuex</h2>
    <div>
      <el-button type="primary" @click="add">点我加1</el-button>
      <p>{{num}}</p>
      <el-button type="warning" @click="toViewPort">跳转至在线预览文档</el-button>
    </div>
  </div>
</template>

<script>
// import { mapActions, mapMutations } from 'vuex'
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  computed: {
    num () {
      return this.$store.state.count
    }
  },
  methods: {
    add () {
      this.$store.commit('increment')
    },
    toViewPort () {
      this.$router.push('/viewPort')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-size: .8rem;
  font-weight: normal;
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
p {
  font-size: .5rem;
}
.hello{
  text-align: center;
}
</style>
