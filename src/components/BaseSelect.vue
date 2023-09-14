<script>
// import store from "../store.js";
import axios from "axios";
export default {
  emits: ["filter"],
  data() {
    return {
      selectedArchetype: 'all',
      archetypes: [],
    };
  },
created() {
  this.fetchArchetypes();
},
methods: {
  fetchArchetypes(){
    axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php').then((response) =>{
      // console.log(response.data);
      this.archetypes =response.data;
    })
    .catch((error) => {
      console.error('Error:',error);
    });
  },
  emitFilterEvent(){
    this.$emit("filter", this.selectedArchetype)// Emette l'evento "filter" con il valore selezionato
  }
}
};
</script>

<template>
 <div class="d-flex justify-content-end">
  <select name="status" id="status" class="form-select w-25" v-model="selectedArchetype" @change="emitFilterEvent">
    <option value="all">Tutti gli archetipi</option>
    <option v-for="archetype in archetypes" :value="archetype"> {{ archetype }}</option>
  </select>
 </div>
</template>

<style lang="scss" scoped></style>