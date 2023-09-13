<script>
import axios from 'axios';
import { store } from './data/store';

import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';


export default {
  data(){
    return{
    store,
    };
  },

  components:{ AppHeader, AppMain },

  methods: {
    fetchCards(endpoint) {
      axios.get(endpoint).then((response) =>{
      // console.log(response.data);
      store.cards = response.data.data;
    });
    }
  },

  created(){
   this.fetchCards(store.apiUrl)
  }
};
  
</script>
<template>
  <AppHeader />
  <AppMain />
</template>
<style lang="scss">
@use './styles/general.scss';


</style>