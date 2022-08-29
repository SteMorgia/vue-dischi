<template>
  <div id="app">
    <MyOption/>
    <MyBody/>
  </div>
</template>

<script>
import MyBody from './components/MyBody.vue';
import MyOption from './components/MyOption.vue';



export default {
  name: 'App',
  components: {
    MyBody,
    MyOption
  }
}
</script>

<style lang="scss">
  @import '@/styles/general.scss';
</style>
