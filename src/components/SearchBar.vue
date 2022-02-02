<template>
  <div class="box-bottone">
    <!--
    <input type="text" placeholder="Cerca" v-model="keywordSearch" />
    <button @click="$emit('search', keywordSearch)">Cerca</button>
    -->
    <select
      v-on:change="$emit('select', keywordSearch)"
      v-model="keywordSearch"
    >
      <option value="all">all</option>
      <option v-for="(genere, index) in generi" :key="index" :value="genere">
        {{ genere }}
      </option>
    </select>
  </div>
</template>

<script>
export default {
  props: {
    generi: Array,
  },
  data() {
    return {
      keywordSearch: "",
    };
  },
};
</script>

<style scoped lang="scss">
@import "../style/search.scss";
</style>
