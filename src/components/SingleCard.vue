<template>
    <div class="col">
        <div class="card text-center">
            <img :src="card.poster" class="card-img-top"/>
            <div class="card-body">
                <h3 class="card-title ms_separator">{{card.title}}</h3>
                <p class="card-text mt-4">{{card.author}}</p>
                <p class="card-text fw-bold">{{card.year}}</p>
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

<style>

</style>