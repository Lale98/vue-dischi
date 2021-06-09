<template>
  <div id="app">
    <TopBar />
    <Main />
  </div>
</template>

<script>
import "@fontsource/roboto";
import Main from './components/Main';
import TopBar from './components/TopBar';

export default {
  name: 'App',
  components: {
    Main,
    TopBar
    
  }
}
</script>

<style lang="scss">
  @import './style/general';
  

</style>
