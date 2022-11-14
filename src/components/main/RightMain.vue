<template>
    <div class="container right_main">
        <div class="user user_profile d-flex">
            <img src="../../assets/img/profile.jpg" alt="">
            <div class="user_info">
                <h6>mariorossi</h6>
                <p>mariorossi</p>
            </div>
            <a href="#" class="text-primary">Passa a</a>
        </div>
        <div class="suggested d-flex py-2">
            <p>Suggerimenti per te</p>
            <button class="btn p-0">Mostra tutti</button>
        </div>
        <div class="user suggested_user d-flex">
            <img src="../../assets/img/profile.jpg" alt="">
            <div class="user_info">
                <h6>mariorossi</h6>
                <p>mariorossi</p>
            </div>
            <a href="#">Segui</a>
        </div>
    <BaseFooter/>
    </div>
</template>
<script>
import BaseFooter from '../footer/BaseFooter.vue'
export default {
  components: { BaseFooter },
    name: 'RightMain'
}
</script>
<style lang="scss" scoped>
    .right_main {
        p, h6 {
            margin: 0;
        }
        padding: 1.25rem;
        width: 40%;
        .suggested {
            align-items: center;
            justify-content: space-between;
        }
        .user_profile img {
            width: 3.75rem;
            height: 3.75rem;
            // width: 100%;
        }
        .suggested_user img {
            width: 2.5rem;
            height: 2.5rem;
        }
        .user_profile img,
        .suggested_user img {
            border-radius: 50%;
            margin-right: .9375rem;
        }
    .user {
        align-items: center;
    }
    .user_info {
        flex-grow: 1;
    }
    }
</style>