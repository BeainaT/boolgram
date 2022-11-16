<template>
    <div class="stories_box">
        <img class="rounded-circle" :src="profiles.profile_picture" alt="" />
        <h6>{{ profiles.profile_name }}</h6>
    </div>
</template>

<script>
export default {
    name: "StoriesBlock",
    props: {
        profiles: Object,
    },
};
</script>

<style lang="scss" scoped>
@import "../../assets/style/parts/mixins";

.stories_box {
    text-align: center;
    margin: 0 0.625rem;

    img {
        @include border-rainbow;
        width: 3.125rem;
        height: 3.125rem;
    }

    h6 {
        font-weight: 400;
        margin: 0;
    }
}
</style>