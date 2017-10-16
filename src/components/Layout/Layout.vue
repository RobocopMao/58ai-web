<template>
  <el-container class="app-layout" direction="vertical">
    <app-header />
    <el-main class="app-main">
      <keep-alive>
        <router-view v-if="$route.meta.keepAlive"></router-view>
        <!--<router-view></router-view>-->
      </keep-alive>
      <router-view v-if="!$route.meta.keepAlive"></router-view>
    </el-main>
    <app-footer />
  </el-container>
</template>

<script>
  import Header from '../Header/Header.vue'
  import Footer from '../Footer/Footer.vue'
  export default {
    name: 'appLayout',
    components: {
      appHeader: Header,
      appFooter: Footer
    }
  }
</script>

<style scoped lang="stylus">
  .app-layout {
    .app-main {
      min-height 615px
    }
  }
</style>
