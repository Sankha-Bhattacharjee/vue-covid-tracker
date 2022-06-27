<template>
<section class="base-title">
    <div>{{ titleText }}</div>
    <div>{{ timestamp }}</div>
  </section>
</template>

<script>
export default {
  props: ["titleText", "dataDate"],
  computed: {
    timestamp() {
      const date = new Date(this.dataDate);
      const formattedDate = date.getDate() + "-" + (date.getMonth() + 1) + "-" + date.getFullYear();
      const hour = date.getHours();
      const formattedTime = hour + ":" + date.getMinutes() + " " + (hour < 12 ? "AM" : "PM");
      return formattedDate + " " + formattedTime;
    },
  },
};
</script>

<style scoped>
.base-title{
  text-align: center;
  padding-bottom: 20px;
  font-size: 20px;
}
@media only screen and (max-width: 480px){
  .base-title{
    font-size: 15px;
    font-weight: bold;
  }
}
</style>
