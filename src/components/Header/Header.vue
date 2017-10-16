<template>
  <el-header class="app-header" height="90px">
    <logo />
  </el-header>
</template>

<script>
  import Logo from './Logo.vue'
  export default {
    name: 'appHeader',
    components: { Logo }
  }
</script>

<style lang="stylus" scoped>
  .app-header {
    padding-top 5px
    padding-bottom 5px
    border-bottom 1px solid #22CAB3
  }
</style>
