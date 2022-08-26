<template>
    <div class="container mt-3">
        <div class="row row-cols-5 g-3">
            <SingleCard v-for="(card, index) in cardsList" :key="index" :card="card"/>
        </div>
    </div>
</template>

<script>
import SingleCard from './SingleCard.vue';
import axios from 'axios'

export default {
    name:'MyBody',
    components: {
        SingleCard
    },
    data() {
        return {
            cardsList: [],
            endpoint: 'https://flynn.boolean.careers/exercises/api/array/music'
        }
    },
    created() {
        this.getCards();
    },
    methods: {
        getCards() {
            let that = this;
            axios.get(this.endpoint)
            .then(function (response) {
                that.cardsList = response.data.response;
            })
        }
    }
}
</script>

<style scoped lang="scss">
    .container {
        width:60%;
        display:flex;
        flex-wrap: wrap;;
        justify-content: center;
        align-items:center;
        flex-basis: 20%;
    }
</style>