<template>
    <section class="main_left">
        <div v-if="isLoaded" class="text-center py-2">
            <img src="../../assets/img/spinner.gif" alt="spinner">
        </div>
        <section class="stories rounded bg-white" :class="isLoaded ? 'skeleton_shadows' : ''">
            <StoriesBlock v-for="profile in profiles" :key="profile.id" :profiles="profile"/>
        </section>
        <section class="posts_card" :class="isLoaded ? 'skeleton_shadows' : ''">
            <PostBlock v-for="post in searchUser" :key="post.id" :posts="post" />
        </section>
    </section>
</template>

<script>
import StoriesBlock from '../commons/StoriesBlock.vue';
import PostBlock from '../commons/PostBlock.vue';
import axios from 'axios';
import { EventBus } from '@/main';
export default {
    name: "LeftMain",
    components: { StoriesBlock, PostBlock },
    data() {
        return {
            posts: [],
            profiles: null,
            isLoaded: true,
            searched: '',
        }
    },
    methods: {
        loaderSpin() {
            this.isLoaded = false
        },
    },
    computed: {
        searchUser() {
            return this.posts.filter((e) => e.profile_name.toLowerCase().includes(this.searched.toLowerCase()));
        },
    },
    mounted() {
        setTimeout(this.loaderSpin, 2000);
        EventBus.$on('search from username', (data) => {
            this.searched = data;
        });
        axios.get('https://flynn.boolean.careers/exercises/api/boolgram/posts')
        .then((res) => {
            this.posts = res.data;
        });
        axios.get('https://flynn.boolean.careers/exercises/api/boolgram/profiles')
            .then((res) => this.profiles = res.data)
            .catch((e) => console.log(e));
    }
}
</script>

<style lang="scss" scoped>
::-webkit-scrollbar {
    width: .3125rem;
    height: .625rem;

    &-track {
        background: var(--bs-gray-200);
    }

    &-thumb {
        background: var(--bs-gray-400);
        border-radius: .3125rem;
    }
}

.main_left {
    width: 55%;

    .skeleton_shadows {
        opacity: 0.3;
        filter: grayscale(1);
        color: transparent;
    }

    .stories {
        display: flex;
        border: 1px solid var(--bs-gray-300);
        padding: .9375rem;
        overflow-x: auto;
    }

    .stories,
    .posts_card {
        width: 100%;
    }
}
</style>