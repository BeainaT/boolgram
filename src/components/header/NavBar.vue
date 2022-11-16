<template>
  <div class="header_nav d-flex">
    <i class="fa-regular fa-heart"></i>
    <i class="fa-solid fa-house-chimney"></i>
    <img class="rounded-circle" src="../../assets/img/profile.jpg" alt="user avatar">
  </div>
</template>

<script>
export default {
  name: 'NavBar'
}
</script>

<style lang="scss" scoped>
.header_nav {
  align-items: center;

  :nth-child(2) {
    margin: 0 .9375rem
  }

  img {
    width: 3.125rem;
  }
}
</style>