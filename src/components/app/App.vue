<template>
  <div class="box">
    <h1 class="d-inline">TODO App</h1>
    <div v-if="isActive"><addmovieform @sendBoolen="getBoolen" /></div>
    <div v-else><forma @submit="newData" /></div>
    <todolist v-for="todo in todos" :list="todo" @delete="getId" />
  </div>
</template>
<script lang="ts">
import addmovieform from "../addFormMovie/addmovieform.vue";
import todolist from "../todolists/tolist.vue";
import forma from "../forma/forma.vue";

export default {
  data() {
    return {
      todos: [{ id: 1, name: "Suxrobjon", year: 1998 }],
      isActive: true,
    };
  },
  components: {
    addmovieform,
    todolist,
    forma,
  },
  methods: {
    newData(data: any) {
      this.todos.push(data);
    },
    getBoolen(data: any) {
      console.log(data);

      this.isActive = !data;
    },
    getId(id: any) {
      this.todos = this.todos.filter((todo) => todo.id !== id);
    },
  },
};
</script>
<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.box {
  margin: auto;
  padding: auto;
  width: 70%;
  height: 100%;
  background-color: #f5f5f5;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  align-content: center;
  border-radius: 5px;
}
</style>
