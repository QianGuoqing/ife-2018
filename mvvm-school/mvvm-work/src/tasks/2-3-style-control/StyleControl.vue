<template>
  <div>
    <div 
      class="block"
      :class="{blue: isActived}"></div>
    <button 
      class="btn btn-primary" 
      @click="toBlue">改变class是背景色变蓝</button>
    <button class="btn btn-danger">改变style是背景色变红</button>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        isActived: false
      }
    },
    methods: {
      toBlue() {
        this.isActived = !this.isActived
      }
    },
  }
</script>

<style scoped>
  .blue {
    background: deepskyblue !important;
  }
  .block {
    width: 100px;
    height: 100px;
    background: #000;
    margin-bottom: 10px;
  }
</style>