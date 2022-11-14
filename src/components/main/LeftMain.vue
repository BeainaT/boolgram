<template>
    <div class="left_main">
        <StoriesBlock/>
        <PostBlock/>
    </div>
</template>

<script>
import StoriesBlock from './StoriesBlock.vue';
import PostBlock from './PostBlock.vue';
   export default {
    name: "LeftMain",
    components: { StoriesBlock, PostBlock }
}
</script>

<style lang="scss">

.left_main {
    width: 60%;
}
</style>