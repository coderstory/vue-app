<template>
  <div id="app">
    <!-- 组件中应用组件，并给子组件传值 -->
    <todo-list :todos="todoData" />
  </div>
</template>
<script>
// 导入组件
import todoList from "./components/todoList";
export default {
  // 组件的名称
  name: "app",
  // 绑定的数据源
  data() {
    return {
      msg: "",
      todoData: [
        {
          id: 1,
          title: "first",
          completed: true
        },
        { id: 2, title: "2", completed: true },
        { id: 3, title: "3", completed: true }
      ]
    };
  },
  components: {
    //声明使用这个组件
    todoList
  }
};
</script>
<style lang="scss"></style>
