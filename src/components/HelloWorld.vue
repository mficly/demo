<template>
  <div class="hello">
    
  </div>
</template>

<script>
/* eslint-disable */
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  created(){
    this.sort();
  },
  methods:{
    sort(){
      this.$axios.get("http://5c92dbfae7b1a00014078e61.mockapi.io/owners").then(result=>{     
        let male = result.data.filter(re=>re.gender=="Male").map(data=>data.name).sort();
        let female = result.data.filter(re=>re.gender=="Female").map(data=>data.name).sort();
        console.log("Male: " + male);
        console.log("Female: " + female);
      });
    }
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
