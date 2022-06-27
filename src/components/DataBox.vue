<template>
  <section class="data-item">
    <h3 class="box-title">{{ boxTitle }}</h3>
    <div>
      <span>New : </span>
      <strong>{{ newCases }}</strong>
    </div>
    <div>
      <span>Total : </span>
      <strong>{{ totalCases }}</strong>
    </div>
  </section>
</template>

<script>
export default {
  props: ["boxTitle", "newCases", "totalCases"],

};
</script>

<style scoped>
.data-item{
    background-color: rgb(189, 133, 244);
    text-align: center;
    padding: 20px;
    border-radius: 25px;
    width: 350px;
    height: 200px;
    box-shadow: 3px 3px 3px grey;
}
.box-title{
    font-size: 40px;
    color: rgb(89, 36, 235);
    padding-bottom: 2rem;
}
span{
    font-size: 20px;
    color: rgb(232, 215, 243);
    font-weight: bold;
}
@media only screen and (max-width: 768px) and (min-width: 481px){
.data-item{
  width: 275px;
  height: 150px;
}
.box-title{
  font-size: 30px;
}
span{
  font-size: 15px;
}
}
@media only screen and (max-width: 480px) {
.data-item{
  width: 250px;
  height: 150px;
}
.box-title{
  font-size: 25px;
}
span{
  font-size: 12px;
}
}
</style>


