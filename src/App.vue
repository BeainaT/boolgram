<template>
  <div id="app">
    <BaseHeader/>
    <BaseMain/>
  </div>
</template>

<script>

import BaseHeader from './components/header/BaseHeader.vue';
import BaseMain from './components/main/BaseMain.vue';

export default {
  name: 'App',
  components: {
    BaseHeader,
    BaseMain,
}
}
</script>

<style lang="scss">
@import './assets/style/global.scss';

</style>
