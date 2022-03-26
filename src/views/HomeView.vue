<template>
  
  <div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
    <h3>This is HomeView</h3>
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
  
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorldComponent.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld
  }
}
</script>

<style scoped>


</style>