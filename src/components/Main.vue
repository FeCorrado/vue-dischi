<template>
  <div class="big">
    <div v-if="!loading" class="boxbb">
      <Card
        v-for="(disco, index) in dischi"
        :key="index"
        class="card"
        :immagine="disco.poster"
        :titolo="disco.title"
        :autore="disco.author"
        :anno="disco.year"
      />
    </div>
    <div v-else>
      <div class="lds-roller">
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
      </div>
    </div>
  </div>
</template>

<script>
import Card from "./Card.vue";
export default {
  components: {
    Card,
  },
  props: {
    dischi: Array,
    loading : Boolean
  },
};
</script>

<style lang="scss">
@import "../style/main.scss";
</style>
