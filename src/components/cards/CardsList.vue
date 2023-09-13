<script>
import Card from './Card.vue';
import { store } from '../../data/store.js';
export default {
  data(){
    return{
    store,
    };
  },
  components: { Card},
};
</script>
<template>
  <section class="container mt-5">


  <div class="row g-4 row-cols-3 row-cols-md-5 row-cols-1g-7">
      <!-- <div class="col" v-for="(card, id) in cards" :key="id">
        <img :src="card.card_images[0].image_url" alt="Card Image" />
        <p class="name">{{ card.name }}</p>
        <p>{{ card.archetype }}</p>
    </div>  -->

    <Card 
    v-for="(card, id) in store.cards" :key="id"
    
    :image="card.card_images[0].image_url"
    :name="card.name"
    :archetype="card.archetype"
    />
  </div>
  </section>
    
 
</template>
<style lang="scss" scoped>
.name{
  color: white;
  width: 300px;
  font-weight: bolder;
}




</style>