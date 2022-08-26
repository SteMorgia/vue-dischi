<template>
  <div id="app">
    <MyBody/>
  </div>
</template>

<script>
import MyBody from './components/MyBody.vue'



export default {
  name: 'App',
  components: {
    MyBody
  }
}
</script>

<style lang="scss">
  @import '@/styles/general.scss';
</style>
