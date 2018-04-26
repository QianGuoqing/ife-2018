<template>
  <div>
    <button class="btn btn-primary" @click="addItem">添加</button>
    <transition-group tag="ul" name="slide">
      <li class="list-group-item" v-for="(item, index) in info" :key="index" @click="showModal(item)">
        <span>{{ item }}</span>
        <button @click="deleteItem(index)" class="btn btn-danger btn-sm pull-right">删除</button>
      </li>
    </transition-group>
    <modal :is-show="show" :content="content" @close="handleClose"></modal>
  </div>
</template>

<script>
  import Modal from './Modal.vue'
  export default {
    components: {
      Modal
    },
    data() {
      return {
        info: [
          'aaaa',
          'bbbb',
          'cccc',
          'dddd',
          'eeee'
        ],
        show: false,
        content: ''
      }
    },
    methods: {
      deleteItem(index) {
        this.info.splice(index, 1)
      },
      addItem() {
        this.info.push('random string')
      },
      showModal(value) {
        this.content = value
        this.show = true
      },
      handleClose(value) {
        this.show = value
      }
    },
  }
</script>

<style scoped>
  li {
    position: relative;
  }
  
  li:hover {
    cursor: pointer;
  }

  .slide-enter {
    opacity: 0;
  }

  .slide-enter-to {
    opacity: 1;
  }
  
  .slide-leave {
    transform: translateX(0);
  }
  
  .slide-leave-to {
    transform: translateX(-200px);
  }
  
  .slide-leave-active,
  .slide-enter-active {
    transition: all .5s;
  }

  li button {
    position: absolute;
    right: 10px;
  }
</style>