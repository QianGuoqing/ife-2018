<template>
  <div>
    <button @click="toggle" class="btn btn-primary">Toggle</button>
    <transition name="fade">
      <div v-show="isShow" class="block"></div>
    </transition>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        isShow: true
      }
    },
    methods: {
      toggle() {
        this.isShow = !this.isShow
      }
    },
  }
</script>

<style scoped>
  .block {
    width: 100px;
    height: 100px;
    background: deeppink;
    margin-top: 10px;
  }
  .fade-enter,
  .fade-leave-to {
    opacity: 0;
  }
  .fade-leave,
  .fade-enter-to {
    opacity: 1;
  }
  .fade-enter-active,
  .fade-leave-active {
    transition: all .5s;
  }
</style>