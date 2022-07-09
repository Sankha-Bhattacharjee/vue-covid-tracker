<template>
  <div v-if="!loading">
    <base-title :title-text='title' :data-date='dataDate'/>
    <base-data-box :stats='stats' />
    <select-history v-if="showHistory" :lastFiveHistory='getLastFiveHistory'/>
    <countries-select :countries="countries" @get-country="getCountryData" @get-history="getHistoryData"/>
    <base-button v-if="showClearButton" @click="clearCountryDataAndHistory" button-title="Clear"/>
  </div>
  <loader v-else/>
  
</template>

<script>
import BaseTitle from '../components/BaseTitle.vue';
import Loader from '../components/Loader.vue';
import BaseDataBox from '../components/BaseDataBox.vue';
import CountriesSelect from '../components/CountriesSelect.vue';
import BaseButton from '../components/BaseButton.vue';
import SelectHistory from '../components/SelectHistory.vue';

export default {
  //name: 'HomeView',
  components: {
    BaseTitle,
    Loader,
    BaseDataBox,
    CountriesSelect,
    BaseButton,
    SelectHistory
  },
  data(){
    return {
      loading: true,
      title: 'Global',
      dataDate:'',
      stats: {},
      countries: [],
      history: [],
      showHistory: false,
    }
  },
  computed:{
    showClearButton(){
      return this.title !== 'Global';
    },
    getLastFiveHistory(){
      const historyLength = this.history.length;
      return historyLength < 5 ? this.history : this.history.slice(historyLength - 5);
    }
  },
  methods:{
    async fetchData(){
      const res =  await fetch('https://api.covid19api.com/summary');
      const data = res.json();
      return data;
    },
    getCountryData(country){
      this.title = country.Country;
      this.dataDate = country.Date;
      const countryStats = {
        'NewConfirmed': country.NewConfirmed,
        'TotalConfirmed':country.TotalConfirmed,
        'NewDeaths':country.NewDeaths,
        'TotalDeaths':country.TotalDeaths
      }
      //console.log(countryStats)
      this.stats = countryStats;
    },
    async clearCountryDataAndHistory(){
      this.loading = true;

      const data = await this.fetchData();
      this.title = 'Global';
      this.dataDate = data.Date;
      this.stats = data.Global;
      this.loading = false;
      
      this.showHistory = false;
    },
    getHistoryData(historyData){
      //console.log('historydata',historyData);
      this.showHistory = true;
      this.history = historyData;
    },
  },
  async created(){
    //console.log('created');
    const data = await this.fetchData();
    
    this.dataDate = data.Date;
    this.stats = data.Global;
    this.countries = data.Countries;
    this.loading = false;
   //console.log(data.Countries);

  }
}
</script>
