<template>
    <div class="container d-flex">
        <LogoApp/>
        <SearchBar/>
        <NavBar/>
    </div>
</template>

<script>
import LogoApp from './LogoApp.vue';
import NavBar from './NavBar.vue';
import SearchBar from './SearchBar.vue';

    export default {
    name: "BaseHeader",
    components: { LogoApp, SearchBar, NavBar }
}
</script>