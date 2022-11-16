<template>
    <div class="post post_container my-3 rounded d-flex bg-white">
        <div class="post_top d-flex align-items-center py-2 px-3">
            <img class="rounded-circle" :src="posts.profile_picture" :alt="posts.profile_fullname" />
            <h5 class="flex-grow-1 mb-0 px-2">{{ posts.profile_name }}</h5>
            <i class="fa-solid fa-ellipsis"></i>
        </div>
        <div class="post_image">
            <img :src="posts.post_image" alt="" />
        </div>
        <div class="post_bottom d-flex p-2">
            <div class="post_bottom_left flex-grow-1">
                <i class="fa-regular fa-heart"></i>
                <i class="fa-regular fa-comment"></i>
                <i class="fa-solid fa-location-arrow"></i>
            </div>
            <div class="post_bottom_right">
                <i class="fa-regular fa-bookmark"></i>
            </div>
        </div>
        <div class="post_reaction px-3 py-2">
            <img class="rounded-circle" :src="posts.likes[posts.likes.length - 1].profile_picture"
                :alt="posts.likes[posts.likes.length - 1].username" />
            <template v-if="posts.likes.length > 2">
                <span>
                    Piace a
                    <strong>{{ posts.likes[posts.likes.length - 1].username }}</strong> e
                    <strong>altre {{ posts.likes.length }}</strong> persone</span>
            </template>
            <template v-else-if="posts.likes.length <= 2">
                <span>
                    Piace a
                    <strong>{{ posts.likes[posts.likes.length - 1].username }}</strong> e
                    <strong>{{ posts.likes.length }} altra </strong> persona</span>
            </template>
            <br />
        </div>
        <div class="px-3 pb-2">
            <strong>{{ posts.profile_name }}</strong> {{ posts.post_text }}
            <br />
            <button class="btn_comments btn p-0" @click="toggleShow()">
                <strong>{{ isShowBtn(posts.comments.length) }}</strong>
            </button>
            <template v-if="showComments">
                <div v-for="comment in posts.comments" :key="comment.id">
                    <strong>{{ comment.username }}</strong> {{ comment.text }}
                </div>
            </template>
            <template v-else>
                <div v-for="comment in firstComments" :key="comment.id">
                    <strong>{{ comment.username }}</strong> {{ comment.text }}
                </div>
            </template>
            <div></div>
        </div>
        <div class="post_comment">
            <i class="fa-regular fa-smile"></i>
            <input type="text" placeholder="Aggiungi un commento..." />
            <button class="btn">Pubblica</button>
        </div>
    </div>
</template>
<script>
export default {
    name: "PostBlock",
    props: {
        posts: Object,
    },
    data() {
        return {
            filtered: [...this.posts.comments],
            showComments: false,
        };
    },
    methods: {
        filteredComments() {
            return this.filtered.splice(0, 3);
        },
        toggleShow() {
            this.showComments = !this.showComments;
        },
        isShowBtn(length) {
            let showBtn;
            if (this.showComments && length > 3) {
                showBtn = "riduci commenti";
            } else if (!this.showComments && length > 3) {
                showBtn = `visualizza ${length} commenti`;
            } else {
                return length == 1
                    ? (showBtn = `il post ha ricevuto ${length} commento`)
                    : `il post ha ricevuto ${length} commenti`;
            }
            return showBtn;
        },
    },
    computed: {
        firstComments() {
            return this.posts.comments.length > 3
                ? this.filteredComments()
                : this.posts.comments;
        },
    },
};
</script>
<style lang="scss">
@import '../../assets/style/parts/mixins';

.post {
    border: 1px solid var(--bs-gray-300);
    flex-direction: column;

    .btn_comments {
        color: inherit;
        font-weight: 400;
    }

    &_top {
        & h5 {
            font-size: 1.125rem;
        }

        & i {
            font-size: 1.25rem
        }

        & img {
            @include border-rainbow;
            width: 3.125rem;
            height: 3.125rem;
        }
    }

    &_reaction img {
        width: 2.5rem;
        height: 2.5rem;
        margin-right: 0.625rem;
    }

    &_image img {
        width: 100%;
    }

    &_comment {
        display: flex;
        align-items: center;
        border-top: 1px solid #cecece;

        input {
            border: none;
            flex-grow: 1;
        }
    }

    &_comment i,
    &_bottom i {
        margin: 0.625rem;
    }
}
</style>