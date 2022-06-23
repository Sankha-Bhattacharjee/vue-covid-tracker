<template>
  <select v-model="selected" class="country-dropdown" @change="onCountrySelect">
    <option value="0" selected disabled>Select Country</option>
    <option
      v-for="country in countries"
      :key="country.ID"
      :value="country.ID"
    >
      {{ country.Country }}
    </option>
  </select>
</template>

<script>
export default {
  props: ['countries'],
  emits:['get-country','get-history'],
  data() {
    return {
      selected: "",
      selectHistory:[],
    };
  },
  methods:{
      onCountrySelect(){
          const country = this.countries.find((item) => item.ID === this.selected);         
          console.log(country);
          if(country){
            this.selectHistory.push(country.Country);
            console.log('history',this.selectHistory);
            this.$emit('get-history',this.selectHistory);
            this.$emit('get-country',country);
          }
      }
  }
};
</script>

<style scoped>
.country-dropdown {
  width: 50%;
  text-align: center;
  display: block;
  margin: 20px auto 0 auto;
  border: 1px solid black;
  background-color: none;
}
</style>
