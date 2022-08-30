<template>
    <div class="container mt-3">
        <div class="row row-cols-5 g-3">
            <SingleCard v-for="(discItem, index) in filteredDiscs" :key="index" :disc="discItem"/>
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
            genres: [],
            endpoint: 'https://flynn.boolean.careers/exercises/api/array/music'
        }
    },
    props: {
        genreToSearch: String
    },
    computed: {
        filteredDiscs() {
            if(this.genreToSearch == '') {
                return this.cardsList;
            } else {
                const arrayDiscs = this.discs.filter(disc => {
                    if (disc.genre == this.genreToSearch) {
                        return true;
                    } else {
                        return false;
                    }
                });
                return arrayDiscs;
            }
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
                let arrayGeners = [];
                that.cardsList = response.data.response;
                that.cardsList.forEach(element => {
                    if (!arrayGeners.includes(element.genre)) {
                        arrayGeners.push(element.genre)
                    }
                } )
                that.$emit('setGeneri', arrayGeners);
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