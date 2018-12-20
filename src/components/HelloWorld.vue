<template>
  <div class="hello">
  {{newsListShow}}
  </div>
</template>

<script>
import api from './../axios/api.js'
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      newsListShow:{}
    }
  },
  mounted(){
    api.JH_news('/CJConditionSetting')
.then(res => {
  let self=this
console.log(res);
self.newsListShow = res.articles;
});
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
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
</style>
