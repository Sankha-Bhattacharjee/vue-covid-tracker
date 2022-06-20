<template>
  <div v-if="!loading">
    <base-title :title-text='title' :data-date='dataDate'/>
    <base-data-box :stats='stats' />
  </div>
  <loader v-else/>
</template>

<script>
import BaseTitle from '../components/BaseTitle.vue';
import Loader from '../components/Loader.vue';
import BaseDataBox from '../components/BaseDataBox.vue';

export default {
  //name: 'HomeView',
  components: {
    BaseTitle,
    Loader,
    BaseDataBox
  },
  data(){
    return {
      loading: true,
      title: 'Global',
      dataDate:'',
      stats: {},
      countries: []
    }
  },
  methods:{
    async fetchData(){
      const res =  await fetch('https://api.covid19api.com/summary');
      const data = res.json();
      return data;
    }
  },
  async created(){
    console.log('created');
    const data = await this.fetchData();
    
    this.dataDate = data.Date;
    this.stats = data.Global;
    this.countries = data.Countries;
    this.loading = false;

  }
}
</script>
