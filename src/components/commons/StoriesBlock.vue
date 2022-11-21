<template>
    <div class="stories_box">
        <div class="toggle_sories" :class="zoomImg ? 'd-none' : ''">
            <img class="rounded-circle" :class="!isShown ? '' : 'img_shown'" :src="profiles.profile_picture" :alt="profiles.profile_name" @click="showStory()">
            <h6>{{ profiles.profile_name }}</h6>
        </div>
        <div class="toggle_img rounded" :class="!zoomImg ? 'd-none' : ''">
            <img :src="profiles.profile_picture" :alt="profiles.profile_name" @click="showStory()">
            <span>posted by {{profiles.profile_name}}</span>
        </div>

    </div>
</template>

<script>
export default {
    name: "StoriesBlock",
    props: {
        profiles: Object,
    },
    data() {
        return {
            zoomImg: false,
            isShown: false
        }
    },
    methods: {
        showStory() {
            this.zoomImg = !this.zoomImg;
            this.isShown = true
        }
    }
};
</script>

<style lang="scss" scoped>
@import "../../assets/style/parts/mixins";

.stories_box {
    text-align: center;
    margin: 0 0.625rem;
    .toggle_img {
        width: 12.5rem;
        height: 12.5rem;
        position: relative;
        overflow: hidden;
        img {
            width: 100%;
            height: 100%;
            border: none;
            filter: brightness(0.5);
        }
        span {
            color: #fff;
            position: absolute;
            bottom: 0;
            left: 50%;
            padding-bottom: .625rem;
            transform: translateX(-50%);
        }
    }

    img {
        @include border-rainbow;
        width: 3.125rem;
        height: 3.125rem;
        &:hover {
            cursor: pointer;
        }
        &:active {
            transform: scale(1.5);
            transition: 2s linear;
        }
        &.img_shown {
            border: 2px solid var(--bs-gray-500);
        }
    }

    h6 {
        font-weight: 400;
        margin: 0;
    }

}
</style>