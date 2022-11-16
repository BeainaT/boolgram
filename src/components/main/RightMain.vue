<template>
    <div class="right_main">
        <div class="user d-flex">
            <img class="rounded-circle" src="../../assets/img/profile.jpg" alt="">
            <div class="user_info">
                <h6>Mario Rossi</h6>
                <p>mariorossi</p>
            </div>
            <button class="btn">Passa a</button>
        </div>
        <div class="suggested d-flex py-4">
            <p class="suggested_p">Suggerimenti per te</p>
            <button class="btn suggested_btn">Mostra tutti</button>
        </div>
        <SuggestedUsers v-for="user in users" :key="user.id" :users="user" />
        <BaseFooter />
    </div>
</template>
<script>
import SuggestedUsers from '../commons/SuggestedUsers.vue'
import BaseFooter from '../footer/BaseFooter.vue'
import axios from 'axios';
export default {
    components: { BaseFooter, SuggestedUsers },
    name: 'RightMain',
    data() {
        return {
            users: null
        }
    },
    methods: {
        apiCall() {
            axios.get('https://flynn.boolean.careers/exercises/api/boolgram/posts')
                .then((res) => this.users = res.data)
                .catch((e) => console.log(e))
        }
    },
    mounted() {
        setTimeout(this.apiCall, 2000)
    }
}
</script>
<style lang="scss" scoped>
.right_main {
    padding: 1.25rem 0;
    width: 40%;

    button {
        font-size: .875rem;
    }

    .user {
        align-items: center;

        & img {
            width: 3.125rem;
            height: 3.125rem;
            margin-right: .9375rem;
        }

        &_info {
            flex-grow: 1;
            font-size: 1.125rem;

            & p {
                color: var(--bs-gray-600)
            }

            &>* {
                margin: 0
            }
        }
    }

    .suggested {
        align-items: center;
        justify-content: space-between;

        &_p {
            color: var(--bs-gray-600);
            font-weight: 600;
            margin: 0
        }

        &_btn {
            color: var(--bs-gray-900)
        }
    }
}
</style>