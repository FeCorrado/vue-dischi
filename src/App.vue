<template>
  <div id="app">
    <Head />
    <SearchBar @select="filterResult" :generi="generi" />
    <Main :dischi="dischiFiltrati" :loading="loading" />
  </div>
</template>

<script>
import axios from "axios";
import Head from "./components/Header.vue";
import SearchBar from "./components/SearchBar.vue";
import Main from "./components/Main.vue";

export default {
  name: "App",
  components: {
    Main,
    Head,
    SearchBar,
  },
  data() {
    return {
      dischi: [],
      dischiFiltrati: [],
      generi: [],
      loading: true,
    };
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((response) => {
        this.dischi = response.data.response;
        this.dischiFiltrati = response.data.response;
        this.filtereGenere(this.dischi);
        this.loading = false; //
      });
  },
  methods: {
    filtereGenere(dischi) {
      for (let i = 0; i < dischi.length; i++) {
        if (!this.generi.includes(dischi[i].genre)) {
          this.generi.push(dischi[i].genre);
        }
      }
    },

    filterResult(keywordSearch) {
      console.log(keywordSearch);
      this.dischiFiltrati = this.dischi.filter((disco) => {
        if (keywordSearch === "all") {
          return disco.genre.includes("");
          //return bottone;
        } else {
          return disco.genre === keywordSearch;
        }
      });
      //filterResult(keyword) {
      //  this.dischiFiltrati = this.dischi.filter((disco) => {
      //    return disco.genre.toLowerCase().includes(keyword);
      //  });
      //},
    },
  },
};
</script>

<style lang="scss"></style>
