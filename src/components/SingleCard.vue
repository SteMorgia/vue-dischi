<template>
    <div class="col">
        <div class="card text-center" style="width: 8rem; height:18rem;">
            <img :src="card.poster" class="card-img-top"/>
            <div class="card-body">
                <h3 class="card-title">{{card.title}}</h3>
                <p class="card-text">{{card.author}}</p>
                <p class="card-text">{{card.year}}</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name:'SingleCard',
    props: {
        card: Object 
    }
}
</script>

<style scoped lang="scss">
    h3 {
        font-size: 15px;
        color:white;
    }
    p {
        color:white;
    }
    .card {
        background-color: rgb(48, 48, 48);
    }
</style>