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
</style>


