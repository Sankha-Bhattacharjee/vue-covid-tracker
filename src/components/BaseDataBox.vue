<template>
  <div class="data-container">
    <!-- Cases -->
    <data-box box-title="Cases" :new-cases="newConfirmCases" :total-cases="totalCases"/>
    <!-- Deaths -->
    <data-box box-title="Mortality" :new-cases="newConfirmDeaths" :total-cases="totalDeaths"/>
  </div>
</template>

<script>
import DataBox from "./DataBox.vue";
export default {
  props: ["stats"],
  components: {
    DataBox,
  },
  computed: {
    newConfirmCases() {
      return this.formatNumber(this.stats.NewConfirmed);
    },
    totalCases() {
      return this.formatNumber(this.stats.TotalConfirmed);
    },
    newConfirmDeaths() {
      return this.formatNumber(this.stats.NewDeaths);
    },
    totalDeaths() {
      return this.formatNumber(this.stats.TotalDeaths);
    },
  },
  methods: {
    formatNumber(num) {
      return num.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",");
    },
  },
};
</script>

<style scoped>
.data-container {
  display: grid;
  grid-template-columns: auto auto;
  justify-content: center;
  align-content: center;
  gap: 10px;
}

@media only screen and (max-width: 480px) {
  .data-container {
    grid-template-columns: auto;
  }
}
</style>
