<template>
  <select v-model="selected" class="country-dropdown" @click="onCountrySelect">
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
  props: ["countries"],
  emits:['get-country'],
  data() {
    return {
      selected: "",
    };
  },
  methods:{
      onCountrySelect(){
          const country = this.countries.find((item) => item.ID === this.selected);
          console.log(country);
          if(country){
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
