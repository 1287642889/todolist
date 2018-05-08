<template>
  <div id="app">
    <input v-model="inputValue"/>
    <button @click="handleSubmit">提交</button>
    <ul>
      <todo_item v-for="(item,index) of list" :key="index" :content="item" :index="index" @delete="handleDelete"></todo_item>
    </ul>
  </div>
</template>

<script>
import TodoItem from './components/TodoItem'

export default {
  components:{
    todo_item:TodoItem
  },
  data () {
    return {
      inputValue:'',
      list:[]
    }
  },
  methods:{
    //handleSubmit(){}是 handleSubmit:function(){}的简写
    handleSubmit () {
      this.list.push(this.inputValue);
      this.inputValue = '';
    },
    //接收子组件传递过来的参数
    handleDelete (index) {
      this.list.splice(index,1);
    }
  }
}
</script>

<style scoped>


</style>
