<template>
  <div>
 
    <Tab></Tab>
  </div>
</template>

<script>
import Tab from './components/Tabs_menu/Tab.vue';

export default {
  name: 'App',
  components: {
    Tab
  }
}
</script>

<style lang="scss">

  /* временно */
  .wrapper {
    max-width: 1200px;
    margin: 0 auto;
    font-family: Arial;
  }
</style>
