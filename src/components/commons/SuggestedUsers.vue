<template>
    <div>
        <div class="user d-flex pb-3">
            <img class="rounded-circle" :src="users.profile_picture" alt="user avatar">
            <div class="user_info">
                <h6>{{ users.profile_name }}</h6>
                <p>{{ users.profile_fullname }}</p>
            </div>
            <button class="btn">Segui</button>
        </div>
    </div>
</template>
<script>
export default {
    name: 'SuggestedUsers',
    props: {
        users: Object
    }
}
</script>
<style lang="scss" scoped>
.user {
    align-items: center;

    &_info {
        flex-grow: 1;

        &>* {
            margin: 0
        }

        & p {
            color: var(--bs-gray-600)
        }
    }

    img {
        width: 2.5rem;
        height: 2.5rem;
        margin-right: .9375rem
    }
}

.user,
button {
    font-size: .875rem;

}
</style>