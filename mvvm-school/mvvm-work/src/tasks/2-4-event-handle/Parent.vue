<template>
  <div>
    <child :message="message" @sendMessage="getMessageFromChild"></child>
    <div class="alert alert-warning">
      我是父组件：<input type="text" class="form-control" :value="message" @keyup="sendToChild">
    </div>
  </div>
</template>

<script>
  import Child from './Child.vue'
  export default {
    components: {
      Child
    },
    data() {
      return {
        message: '静静等待用户输入'
      }
    },
    methods: {
      getMessageFromChild(value) {
        this.message = value
      },
      sendToChild(e) {
        this.message = e.target.value
      }
    },
  }
</script>

<style scoped>
  .alert {
    margin-top: 10px;
  }
</style>