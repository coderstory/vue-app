<template>
  <div>
    <div v-for="(todo,index) in todos" :key="index">
      <!-- 自定义一个事件del -->
      <todoItem :todo="todo" @delEvent="delItem" />
    </div>
  </div>
</template>
<script>
// 导入代码块
import todoItem from "./todoItem";
export default {
  name: "todoList",
  // 子组件接收来自父组件的数据
  props: {
    todos: Array
  },
  // 声明使用到的组件
  components: {
    todoItem
  },
  // 定义组件独有的方法
  methods: {
    delItem(id) {
      console.log(id);
      this.todos.splice(
        this.todos.findIndex(item => item.id === id),
        1
      );
    }
  }
};
</script>

<style scoped>
</style>