<template>
  <div id="app">
    <Header/>
    <MainSection/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import MainSection from './components/MainSection.vue'

export default {
  name: 'App',
  components: {
    Header,
    MainSection
  }
}
</script>

<style lang="scss">
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
</style>
