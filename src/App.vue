<template>
  <div id="app">
    <AppHeader @ax-data="getApiKey" />
  </div>
</template>

<script>
import AppHeader from './components/AppHeader.vue';
import axios from "axios"

export default {
    name: "App",
    components: { AppHeader },
    data(){
      return{
        author:"eco",
        apiUrl:"https://openlibrary.org/search.json?author="
      }
    },
    methods: {
      getApiKey(key){
        console.log(key)
        this.author = key
        this.getApiData()
      },
      getApiData(){
        axios.get(this.apiUrl + this.author)
        .then(r => console.log(r.data.docs))
      }
    },
    mounted() {
      this.getApiData()
    },
}
</script>

<style lang="scss" >
@import "./assets/styles/global";
</style>
