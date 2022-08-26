<template>
    <div>
        <SingleCard v-for="(card, index) in cardsList" :key="index" :card="card"/>
    </div>
</template>

<script>
import SingleCard from './components/SingleCard.vue';
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
                that.cardsList = response.data;
            })
        }
    }
}
</script>

<style>

</style>