<template>
    <header>
        <div class="container header_container py-2">
            <LogoApp/>
            <SearchBar/>
            <NavBar/>
        </div>
    </header>
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
<style lang="scss" scoped>
header {
    border-bottom: 1px solid #dedede;        
    .header_container {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

}
</style>