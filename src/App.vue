<script>
import axios from 'axios';
import { store } from './data/store';
import BaseSelect from './components/BaseSelect.vue';

import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';


export default {
  data(){
    return{
    store,
    };
  },

  components:{ AppHeader, AppMain,BaseSelect },

  methods: {
    fetchCards(endpoint) {
      axios.get(endpoint).then((response) =>{
      // console.log(response.data);
      this.store.cards = response.data.data;
    });
    }
  },

  created(){
   this.fetchCards(this.store.apiUrl)
  }
};
  
</script>
<template>
  <AppHeader />
  <BaseSelect />
  <AppMain />
</template>
<style lang="scss">
@use './styles/general.scss';


</style>