<template>
    <div class="post post_container my-3">
        <div class="post_top d-flex align-items-center">
            <img src="../../assets/img/profile.jpg" alt="">
            <h5>Mario Rossi</h5>
        </div>
        <div class="post_image">
            <img src="../../assets/img/landscape.png" alt="">
        </div>
        <div class="post_bottom">
            <div class="post_bottom_left">
                <i class="fa-regular fa-heart"></i>
                <i class="fa-regular fa-comment"></i>
                <i class="fa-solid fa-location-arrow"></i>
            </div>
            <div class="post_bottom_right">
                <i class="fa-regular fa-bookmark"></i>
            </div>
        </div>
        <div class="post_comment">
            <i class="fa-regular fa-smile"></i>
            <input type="text" placeholder="Aggiungi un commento...">
            <button class="btn text-primary">Pubblica</button>
        </div>
    </div>
</template>
<script>
export default {
    name: 'PostBlock'
}
</script>
<style lang="scss">
    .post {
        border: 1px solid #cecece;
        display: flex;
        flex-direction: column;
        &_top img {
            width: 2.5rem;
            height: 2.5rem;
            border-radius: 50%;
            margin: 10px;
        }
        &_image img{
            width: 100%;
        }
        &_bottom {
            display: flex;
            &_left {
                flex-grow: 1;
                :nth-child(2) {
                    margin: 0 .625rem;
                }
            }
        }
        &_comment {
            display: flex;
            align-items: center;
            border-top: 1px solid #cecece;
            input {
                border: none;
                outline: none;
                flex-grow: 1;
            }
        }
        &_comment i,
        &_bottom i {
            font-size: 1.5625rem;
            margin: .625rem
        }
    }

</style>