<template>
    <header>
        <select @change="$emit('changedGenre', selectedGenre)" v-model="selectedGenre" class="form-select" aria-label="Default select example">
            <option value="">Seleziona un genere</option>
            <option v-for="(genre, index) in genersType" :key="index" :genre="genre">{{genre}}</option>
        </select>
    </header>
</template>

<script>
export default {
    name: 'MyOption',
    props: {
        genersType: Array
    },
    data() {
        return {
            selectedGenre:''
        }
    }
};
</script>

<style scoped lang="scss">
    header {
        display: flex;
        justify-content: end;

        select {
        margin: 1rem;
        width: 200px;
    }
    }
</style>