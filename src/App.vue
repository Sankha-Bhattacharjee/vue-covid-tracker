<template>

  <Header />
  <div class='container'>
    <router-view/>
  </div>
</template>

<script>
import Header from './components/Header.vue'

export default {
  components:{
    Header
  }
}
</script>

<style>
*{
  margin: 0 auto;
  box-sizing: border-box;
  font-family: sans-serif;
}
.container{
  padding: 2rem;
}
</style>
