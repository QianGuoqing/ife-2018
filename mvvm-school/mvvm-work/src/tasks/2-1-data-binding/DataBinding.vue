<template>
  <div>
    <div class="input-group">
      <input type="text" placeholder="姓名(String)" v-model="information.name">
      <input type="text" placeholder="年龄(Number)" v-model="information.age">
      <input type="text" placeholder="简介(String)" v-model="information.desc">
    </div>
    <div class="remove">
      信息：<button @click="removeInfo" class="remove-button">移除信息</button>
    </div>
    <div class="display">
      <p>姓名: {{ information.name }}</p>
      <p>年龄: {{ information.age }}</p>
      <p>简介: {{ information.desc }}</p>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        information: {
          name: '',
          age: '',
          desc: ''
        }
      }
    },
    methods: {
      removeInfo() {
        this.information = {
          name: '',
          age: '',
          desc: ''
        }
      }
    },
  }
</script>

<style lang="stylus" scoped>
  .remove 
    margin-top 20px
</style>