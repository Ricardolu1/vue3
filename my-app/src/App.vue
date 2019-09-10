<template>
  <div id="app">
    {{msg}}
    <div>
      <input type="text" v-model="info" />
      <button @click="handleClick">添加</button>
      <ul>
        <todo-item v-for="item in list" :key="item" :item="item"></todo-item>
      </ul>
    </div>
  </div>
</template>

<script>
import TodoItem from "./components/TodoItem";
export default {
  name: "app",
  components: {
    TodoItem
  },
  data() {
    return {
      msg: "hello geektime",
      info: "",
      list: []
    };
  },
  methods: {
    handleClick() {
      this.list.push(this.info);
      this.info = "";
    }
  }
};
</script>

<style>
</style>
