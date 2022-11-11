<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <BaseHeader/>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

import BaseHeader from './components/header/BaseHeader.vue';


export default {
  name: 'App',
  components: {
    BaseHeader
}
}
</script>

<style lang="scss">
@import './assets/style/global.scss';

</style>
