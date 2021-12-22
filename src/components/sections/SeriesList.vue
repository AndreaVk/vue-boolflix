<template>
    <section>
        <h2>Serie TV</h2>
        <ul>
            <li v-for="(serie,index) in series" :key="index">
            <Card :info="serie"/>
            </li>
        </ul>
    </section>
</template>

<script>
import Card from '../elements/Card.vue';
export default {
    name:"SeriesList",
    props:{
        series: Array
    },
    components:{
        Card
    }
}
</script>

<style>

</style>