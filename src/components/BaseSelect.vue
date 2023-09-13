<script>
import store from "../store";
import axios from "axios";
export default {
  data() {
    return {
      selectedArchetype: 'all',
      archetype: [],
    };
  },
created() {
  this.fetchArchetypes()
},
methods: {
  
}
};
</script>

<template>
 <div class="d-flex justify-content-end">
  <select name="status" id="status" class="form-select w-25" v-model="selectedArchetype">
    <option value="all">Tutti gli archetipi</option>
    <option v-for="archetype in archetypes" value="archetype"></option>
  </select>
 </div>
</template>

<style lang="scss" scoped></style>