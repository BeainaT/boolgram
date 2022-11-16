<template>
    <main class="container d-flex justify-content-between py-4 px-5">
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