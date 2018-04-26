<template>
  <div id="app">
    <!-- <data-binding></data-binding> -->
    <!-- <condition-loop></condition-loop> -->
    <style-control></style-control>
  </div>
</template>

<script>
  import DataBinding from './tasks/2-1-data-binding/DataBinding.vue'
  import ConditionLoop from './tasks/2-2-condition-loop/ConditionLoop.vue'
  import StyleControl from './tasks/2-3-style-control/StyleControl.vue'
  export default {
    name: 'App',
    components: {
      DataBinding,
      ConditionLoop,
      StyleControl
    }
  }
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin: 60px;
}
</style>
