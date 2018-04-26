<template>
  <div class="card-wrapper">
    <div class="my-card-header">
      <slot name="title"></slot>
    </div>
    <div class="my-card-body">
      <slot name="content"></slot>
    </div>
  </div>
</template>

<script>
  export default {
    
  }
</script>

<style lang="stylus" scoped>
  .card-wrapper
    display inline-block
    border 1px solid #ccc
    border-radius 5px
</style>