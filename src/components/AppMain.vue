<template>
<main class="container">
<h3 class="text-center">Ricerca trovata per "{{apiKey}}"</h3>
<div v-for="(book, index) in books" :key="index+'b'" class="card ">
<p> Titolo: {{book.title}}</p>
<p> Primo anno di pubblicazione: {{book.first_publish_year}}</p>
<p> Lingue tradotte <span v-for="(lang, index) in book.language" :key="index">{{lang}}, </span></p>

</div>
</main>
</template>

<script>
export default {
    name : "AppMain",
    props: {
        books: Array,
        apiKey: String
    }

}
</script>

<style>

</style>