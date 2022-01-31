<template>
  <div id="app">
    <Head />
    <Main :dischi="dischi" :loading="loading" />
  </div>
</template>

<script>
import axios from "axios";
import Main from "./components/Main.vue";
import Head from "./components/Header.vue";

export default {
  name: "App",
  components: {
    Main,
    Head,
  },
  data() {
    return {
      dischi: [],
      loading: true,
    };
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((response) => {
        this.dischi = response.data.response;
        this.loading = false;
      });
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
