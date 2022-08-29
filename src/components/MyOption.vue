<template>
    <header>
        <select class="form-select" aria-label="Default select example">
            <option></option>
        </select>
    </header>
</template>

<script>
export default {
    name: 'MyOption',
    data() {
        return {
            
        }
    }
}
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