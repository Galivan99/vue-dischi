<template>
  <div id="app">
    <div class="contianer">
      <Header/>

      <DiscList/>
    </div>

  </div>
</template>

<script>
import Header from './components/Header.vue'
import DiscList from './components/DiscList.vue'

export default {
  name: 'App',
  components: {
    Header,
    DiscList
  }
}
</script>

<style lang="scss">
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
</style>
