<template>
    <div class="search_bar text-center">
        <input class="rounded" type="text" placeholder="Cerca">
    </div>
</template>

<script>
export default {
    name: 'SearchBar'
}
</script>

<style lang="scss">
    .search_bar {
        flex-grow: 1;
        input {
            text-align: center;
            border: 1px solid #cecece;
        }
    }

</style>