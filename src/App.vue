<template>
  <div id="app">
    <MyOption @changedGenre="startSearch" :genersType="geners"/>
    <MyBody @setGeneri="saveGeners" :genreToSearch="genreToSearch"/>
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
  },
  data(){
    return {
      geners: [],
      genreToSearch: ''
    }
  },
  methods: {
    saveGeners(geners) {
      this.geners = geners
    },
    startSearch(genreToSearch) {
      this.genreToSearch = genreToSearch;
    }
  }
}
</script>

<style lang="scss">
  @import '@/styles/general.scss';
</style>
