<template>
  <div>
    <div class="add">
      <div class="input-group">
        <div class="input-group-prepend">
          <span class="input-group-text">姓名</span>
          <input type="text" class="form-control" v-model="name">
        </div>
      </div>
      <div class="input-group">
        <div class="input-group-prepend">
          <span class="input-group-text">状态</span>
          <input type="text" class="form-control" v-model="status">
        </div>
      </div>
      <div>
        <button @click="addInformation" type="button" class="btn btn-primary">添加</button>
      </div>
    </div>
    <table class="table table-dark">
      <thead>
        <tr>
          <th>姓名</th>
          <th>状态</th>
          <th>操作</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(item, index) in information" :key="index">
          <td>{{ item.name }}</td>
          <td>{{ item.status }}</td>
          <td>
            <button @click="alterInformation(index, $event)" class="btn btn-danger">{{ getOperation(item.status) }}</button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        name: '',
        status: '',
        operation: '',
        information: [
          {
            name: '张三',
            status: '合格',
            operation: '删除'
          },
          {
            name: '李四',
            status: '不合格',
            operation: '删除'
          },
          {
            name: '王五',
            status: '待审核',
            operation: '审核'
          },
          {
            name: '赵六',
            status: '待审核',
            operation: '审核'
          }
        ]
      }
    },
    methods: {
      getOperation(status) {
        if (status === '合格' || status === '不合格') {
          return '删除'
        } else if (status === '待审核') {
          return '审核'
        }
      },
      addInformation() {
        this.information.push({
          name: this.name,
          status: this.status,
          operation: this.getOperation(this.status)
        })
        this.name = ''
        this.status = ''
      },
      alterInformation(index, e) {
        // console.log(e.target.innerText);
        const text = e.target.innerText
        if (text === '删除') {
          this.information.splice(index, 1)
        } else if (text === '审核') {
          this.information[index].status = '合格'
          this.information[index].operation = this.getOperation(this.information[index].status)
        }
      }
    },
  }
</script>

<style lang="stylus" scoped>
  .table
    margin-top 10px
    width 40%
    text-align center
</style>