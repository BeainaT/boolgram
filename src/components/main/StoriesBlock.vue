<template>
    <section class="stories stories_container">
        <div class="stories_box" v-for="(profile, index) in profiles" :key="index">
            <img :src="profile.profile_picture" alt="">
            <h6>{{profile.profile_name}}</h6>
        </div>
    </section>
</template>

<script>
import axios from 'axios';
   export default {
    name: 'StoriesBlock',
    data() {
        return {
            profiles: null,
            currents: 0
        }
    },
    mounted() {
        axios.get('https://flynn.boolean.careers/exercises/api/boolgram/posts')
            .then((res) => this.profiles = res.data)
    }
   }
</script>

<style lang="scss" scoped>
.stories {
    display: flex;
    border: 1px solid #cecece;
    padding: .9375rem;
    overflow-x: auto;
    &_box {
        text-align: center;
        margin: 0 .625rem;
    }
}
    img {
        width: 3.125rem;
        height: 3.125rem;
        border-radius: 50%;
    }

</style>