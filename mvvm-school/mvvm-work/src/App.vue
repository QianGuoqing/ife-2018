<template>
  <div id="app">
    <!-- <data-binding></data-binding> -->
    <!-- <condition-loop></condition-loop> -->
    <!-- <style-control></style-control> -->
    <!-- <event-handle></event-handle> -->
    <!-- <first-transition></first-transition> -->
    <!-- <second-transition></second-transition> -->
    <!-- <life-cycle></life-cycle> -->
    <slot-related>
      <h3 class="task" slot="title">任务一</h3>
      <div class="content" slot="content">
        <div class="title">标题：插槽</div>
        <div class="content">内容：xxxxxx</div>
        <div class="time">时间：2018-04-30</div>
      </div>
    </slot-related>
    <slot-related>
      <h3 class="task" slot="title">任务二</h3>
      <div class="content" slot="content">
        <div class="title">标题：插槽2</div>
        <div class="content">内容：yyyyyyy</div>
        <div class="time">时间：2018-04-30</div>
      </div>
    </slot-related>
  </div>
</template>

<script>
  import DataBinding from './tasks/2-1-data-binding/DataBinding.vue'
  import ConditionLoop from './tasks/2-2-condition-loop/ConditionLoop.vue'
  import StyleControl from './tasks/2-3-style-control/StyleControl.vue'
  import EventHandle from './tasks/2-4-event-handle/EventHandle.vue'
  import FirstTransition from './tasks/2-7-transition-animation/FirstTransition.vue'
  import SecondTransition from './tasks/2-7-transition-animation/SecondTransition.vue'
  import LifeCycle from './tasks/2-8-life-cycle/LifeCycle.vue'
  import SlotRelated from './tasks/2-6-slot-related/SlotRelated.vue'

  export default {
    name: 'App',
    components: {
      DataBinding,
      ConditionLoop,
      StyleControl,
      EventHandle,
      FirstTransition,
      SecondTransition,
      LifeCycle,
      SlotRelated
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
