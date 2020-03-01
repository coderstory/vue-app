<template>
  <div>
    <div :class="todo.completed">
      <p>
        <input type="checkbox" name="cheked" id @change="markFCompleted" />
        {{todo.title}}
        <!-- 触发一个父组件声明的事件 用于调用父组件 -->
        <button @click="$emit('delEvent',todo.id)">Del</button>
      </p>
    </div>
  </div>
</template>
<script>
export default {
  name: "todoItem",
  props: ["todo"],
  methods: {
    markFCompleted() {
      console.log(this.todo.completed);
      this.todo.completed = !this.todo.completed;
    }
  }
};
</script>
<style scoped>
.is-completed {
  text-decoration: line-through;
}
</style>