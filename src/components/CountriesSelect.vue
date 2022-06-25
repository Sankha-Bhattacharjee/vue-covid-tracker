<template>
<section id="county-select-section">
  <label for="country">Select a Country : </label>
  <select name="country" v-model="selected" class="country-dropdown" @change="onCountrySelect">
    <option value="0" selected disabled>Select Country</option>
    <option
      v-for="country in countries"
      :key="country.ID"
      :value="country.ID"
    >
      {{ country.Country }}
    </option>
  </select>
  </section>
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
  width: 60%;
  text-align: center;
  display: inline;
  border: 1px solid black;
  background-color: none;
}
label{
  font-size: 1.5em;
  color: grey;
}
#county-select-section{
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  max-width: 50%;
  padding: 10px 5px;
  border: 2px solid rgb(179, 84, 235);
  border-radius: 10px;
  margin: 20px auto;
  box-shadow: 3px 3px 3px grey;
}
</style>
