<template>
  <li class='item' @click="handle_click">{{content}}</li>
</template>

<script>
export default {
  //接收父组件的传值
  props:['content','index'],
  methods:{
    handle_click(){
      //delete
      //把数据传给父组件
      this.$emit('delete',this.index)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.item{
  color:green;
}
</style>
