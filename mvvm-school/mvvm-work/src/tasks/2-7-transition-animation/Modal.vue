<template>
  <transition name="fade">
    <div v-show="isShow" class="modal-wrapper">
      <div class="content">{{ content }}</div>
      <button class="cclose btn btn-danger btn-sm" @click="closeModal">关闭</button>
    </div>
  </transition>
</template>

<script>
  export default {
    props: {
      isShow: {
        type: Boolean,
        default: false
      },
      content: {
        type: String,
        default: ''
      }
    },
    methods: {
      closeModal() {
        this.$emit('close', false)
      }
    },
  }
</script>

<style lang="stylus" scoped>
  .fade-enter {
    opacity: 0;
  }
  .fade-enter-to {
    opacity: 1;
  }
  .fade-leave {
    opacity: 1;
  }
  .fade-leave-to {
    opacity: 0;
    transform rotate(1.1)
  }
  .fade-leave-active,
  .fade-enter-active {
    transition: all .5s;
  }
  .modal-wrapper 
    display inline-block
    border 1px solid #ccc
    border-radius 5px
    text-align center
    position absolute
    left 50%
    transform translateX(-50%)
    .content
      font-size 24px
      font-weight 700
      padding 20px 30px
    .cclose
      margin-bottom 20px
</style>