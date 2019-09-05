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
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
#signin {
  background-color: green;
  margin-right: 5px;
}
#signup {
  margin-left: 5px;
  background-color: lightblue;
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
.inputs {
  margin-bottom: 10px;
  margin-top: 10px;
  border-radius: 10px;
  padding-left: 5px;
  height: 30px;

}
</style>
