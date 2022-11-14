<template>
    <main class="container d-flex py-3">
        <LeftMain/>
        <RightMain/>
    </main>
</template>
<script>
import LeftMain from './LeftMain.vue';
import RightMain from './RightMain.vue';
export default {
    name: 'BaseMain',
    components: {LeftMain, RightMain}
}

</script>

<style>
</style>