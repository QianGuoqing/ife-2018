<template>
  <div>
    <div class="card">
      <div class="head-card">
        <h1 class="title">expension panel</h1>
        <button @click="toggle" class="btn btn-primary btn-sm">{{ buttonText }}</button>
      </div>
      <transition class="fade">
        <div v-show="isShow" class="card-text">
          Lorem ipsum dolor, sit amet consectetur adipisicing elit. Inventore, debitis commodi a veritatis aut natus et nam odio! Quia architecto officia dolores nobis sed ullam, totam perferendis dolorum dignissimos et?
        </div>
      </transition>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        buttonText: '展开',
        isShow: false
      }
    },
    methods: {
      toggle() {
        this.isShow = !this.isShow
        if (this.isShow) {
          this.buttonText = '收起'
        } else {
          this.buttonText = '展开'
        }
      }
    },
  }
</script>

<style lang="stylus" scoped>
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
  .card
    .head-card
      display flex
      justify-content space-between
      padding 10px
      .title
        font-size 16px
    .card-text
      padding 10px
</style>