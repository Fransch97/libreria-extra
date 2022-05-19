<template>
  <header class="text-center pt-5 pb-5">
      <h1>La Libreria Mondiale</h1>
      <p>Cerca un authore:</p>
      <input @click="inputes" @keyup.enter="enter"  v-model="key" type="text">
  </header>
</template>

<script>
export default {
    name: "AppHeader",
    data() {
        return {
            key: "Cerca un authore"
        }
    },
    methods: {
        inputes(){
            this.key = ""
        },
        enter(){
            this.$emit('ax-data' , this.key )
            this.key = ""
        }
    },
}
</script>

<style>

</style>