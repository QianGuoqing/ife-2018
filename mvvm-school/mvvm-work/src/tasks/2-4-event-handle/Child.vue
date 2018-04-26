<template>
  <div>
    <div class="input-group">
      <div class="input-group-prepend">
        <span class="input-group-text">子组件</span>
      </div>
      <input type="text" class="form-control" v-model="message">
      <button @click="sendMessage" class="btn btn-primary">通知父组件</button>
    </div>
  </div>
</template>

<script>
  export default {
    props: {
      message: {
        type: String,
        default: ''
      },
    },
    data() {
      return {
      }
    },
    methods: {
      sendMessage() {
        this.$emit('sendMessage', this.message)
      }
    },
  }
</script>

<style scoped>

</style>