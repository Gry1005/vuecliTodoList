<template>
  <div>
    <input class="item" v-model="inputValue"/>
    <button @click="handle_submit">提交</button>
    <ul>
      <todo-item v-for="(item,index) of list" :key="index" :content="item" :index="index" @delete="handle_delete"/>
    </ul>
  </div>
</template>

<script>
 import todoItem from './components/todoItem'

export default {
  components:{'todo-item':todoItem},
  //data变为一个函数
  data()
  {
    return{
      inputValue:'',
      list:[]
    }
  },
  methods:{
    handle_submit(){
      this.list.push(this.inputValue);
      this.inputValue='';
    },
    handle_delete(index){
      this.list.splice(index,1);
    }
  }
}
</script>

<style scoped>

</style>
