<template>
    <div>
        <img :src="'https://image.tmdb.org/t/p/w342'+ info.poster_path" :alt="info.title ? info.title : info.name">
        <h3>{{info.title ? info.title : info.name}}</h3>
        <h4 v-if="info.original_title">{{info.original_title}}</h4>
        <h4 v-else >{{info.original_name}}</h4>
        <div>
            <img v-if="flags.includes(info.original_language)" :src="require(`../../assets/flags/${info.original_language}.png`)" :alt="info.original_language" height="15">
            <img v-else src="../../assets/flags/pace.png" alt="" height="15">
        </div>

        <div>{{info.vote_average}}</div>
        <h2>{{info.popularity}}</h2>
    </div>
</template>

<script>
export default {
    name: 'Card',
    props: {
        info: Object
    },
    data(){
        return{
            flags:[
                'it',
                'en',
                'fr'
            ]
        }
    }
}
</script>

<style>
</style>