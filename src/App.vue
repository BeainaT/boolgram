<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <BaseHeader/>
    <BaseMain/>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

import BaseHeader from './components/header/BaseHeader.vue';
import BaseMain from './components/main/BaseMain.vue';


export default {
  name: 'App',
  components: {
    BaseHeader,
    BaseMain
}
}
</script>

<style lang="scss">
@import './assets/style/global.scss';

</style>
