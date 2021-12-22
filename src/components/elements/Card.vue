<template>
    <div>
        <h3>{{info.title}}</h3>
        <h4>{{info.original_title}}</h4>
        <div><img v-if="flags.includes(info.original_language)" :src="require(`../../assets/flags/${info.original_language}.png`)" :alt="info.original_language" height="15">
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