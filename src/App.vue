<template>
  <div id="app">
    <AppHeader @ax-data="getApiKey" />
  </div>
</template>

<script>
import AppHeader from './components/AppHeader.vue';

export default {
    name: "App",
    components: { AppHeader },
    data(){
      return{
        author:"eco",
      }
    },
    methods: {
      getApiKey(key){
        console.log(key)
        this.author = key
      }
    },
}
</script>

<style lang="scss" >
@import "./assets/styles/global";
</style>
