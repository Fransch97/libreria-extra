<template>
  <div id="app">
    <AppHeader @ax-data="getApiKey" />
    <AppMain :apiKey="author" :books= "books"/>
  </div>
</template>

<script>
import AppHeader from './components/AppHeader.vue';
import axios from "axios"
import AppMain from "./components/AppMain.vue"

export default {
    name: "App",
    components: { AppHeader, AppMain },
    data(){
      return{
        author:"eco",
        apiUrl:"https://openlibrary.org/search.json?author=",
        books: []
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
        .then(r =>{
          this.books = r.data.docs
          console.log(this.books)
        })
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
