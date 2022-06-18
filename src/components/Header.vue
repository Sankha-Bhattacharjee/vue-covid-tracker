<template>
  <header class='header'>
    <div id='title-text'><i class="fa fa-viruses"></i>Covid-19 Tracker</div>
    <p>API link: <a href="https://covid19api.com" target="_blank">covid19api</a></p>
  </header>
</template>

<script>
export default {
  name: 'Header',

}
</script>
<style scoped>
.header{
  text-align: center;
  color: white;
  background-color: blueviolet;
  margin-bottom: 10px;
}
#title-text{
  font-size: xx-large;
  font-weight: bold;
  padding: 10px;
  margin-bottom: 5px;
}
p{
  padding-bottom: 5px;
}
a{
  color: violet;
  text-decoration: none;
}
a:hover{
  color: white;
}
</style>

