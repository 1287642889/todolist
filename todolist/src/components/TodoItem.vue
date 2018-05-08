<template>
  <div>
    <li @click="handleDelete" class="item">{{content}}</li>
  </div>
</template>

<script>
export default {
  //props用来接收父组件传递过来的参数
  props:['content','index'],
  methods:{
    handleDelete () {
      //子组件与父组件通信
      this.$emit('delete',this.index);
    }
  }
}
</script>

<!--scoped:该样式是局部样式，只对本文件有效-->
<style scoped>
  .item {
    color:red;
  }
</style>
