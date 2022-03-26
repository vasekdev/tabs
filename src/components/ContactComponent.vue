<template>
   <span class="redText"> ------------------ ContactComponent-start ------------------ </span>
  <div class="hello">
    <h3>{{ msg }}</h3>
    <p>
      <!-- <a href="javascript:void(0)" @click="addWindow('https://www.google.com','Google')">Google</a> |  -->
      <a href="javascript:void(0)" @click="addWindow('https://www.wikipedia.org','Wiki')">wiki</a> | 
      <a href="javascript:void(0)" @click="addWindow('https://www.britannica.com','Britannica')">Britannica</a> | 
      <a href="javascript:void(0)" @click="addWindow('https://www.encyclopedia.com','Encyclopedia')">Encyclopedia</a><br />
      <a href="javascript:void(0)" @click="closeWindows">sign out</a>
    </p>
  </div>
  <span class="redText"> ------------------ ContactComponent-end ------------------ </span>
</template>

<script>
export default {
  name: 'ContactComponent',
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
.redText{
  color: red;
}
</style>
