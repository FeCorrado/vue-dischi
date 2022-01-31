<template>
  <div id="app">
    <Main :disco="dischi"/>
  </div>
</template>

<script>
import axios from 'axios'
import Main from './components/Main.vue'

export default {
  name: 'App',
  components: {
    Main,
  },
  data() {
    return{
      dischi: []
    }
  },
    mounted() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((response)=>{
          this.dischi = response.data
        })
}
}

</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>