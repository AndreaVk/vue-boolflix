<template>
    <main>
        <input type="text" v-model="searchFilm">
        <button  @click="ricerca">Cliccami</button>
        <ul v-for="(films, i) in film" :key="i">
            <li>{{films.title}}</li>
            <li>{{films.original_title}}</li>
            <li>{{films.original_language}}</li>
            <li>{{films.vote_average}}</li>
        </ul>
    </main>
</template>

<script>
import axios from 'axios';
export default {
name: 'Main',
data(){
    return {
        film: [],
        searchFilm: ''
    }
},
methods: {
    ricerca() {
    axios.get('https://api.themoviedb.org/3/search/movie', {
    params: {
        api_key: '4e788affa1e0f1509f04bf2975a1f73c',
        query: this.searchFilm,
        language: 'it-IT'
    }
    })
    .then((response) => {
    console.log(response.data.results);
    this.film = response.data.results
    console.log(this.film);
    })
    .catch(function (error) {
    console.log(error);
    })
    }
}
}
</script>

<style>
</style> 
0 comments on commit 793e902