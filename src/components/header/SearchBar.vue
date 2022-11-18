<template>
    <div class="search_bar text-center">
        <input class="rounded" type="text" placeholder="Cerca" @keyup="passText(searchingFor)" v-model="searchingFor">
    </div>
</template>

<script>
import { EventBus } from '@/main';
export default {
    name: 'SearchBar',
    data() {
        return {
            searchingFor: ''
        }
    },
    methods: {
        passText(str) {
            EventBus.$emit('search from username', str)
        }
    }
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