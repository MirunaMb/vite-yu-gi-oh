<script>

export default {
    props: {
        image: String,
        name: String,
        archetype: String,
    }
};
</script>
<template>
   <div class="col">
        <img :src="image" alt="Card Image" />
        <p class="name">{{ name }}</p>
        <p>{{ archetype }}</p>
    </div> 
</template>
<style lang="scss" scoped>
.name{
  color: white;
  width: 300px;
  font-weight: bolder;
}

</style>