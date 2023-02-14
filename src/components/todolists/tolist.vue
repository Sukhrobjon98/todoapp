<template>
  <ul class="list list-group">
    <li :key="list.id">
      <span>Ismi: {{ list.name }}</span>
      <span> Yili: {{ list.year }}</span>
      <button class="btn"><i class="bi bi-pencil-square"></i></button>
      <button @click="deleteIteam" class="btn">
        <i class="bi bi-trash"></i>
      </button>
    </li>
  </ul>
</template>
<script lang="ts">
export default {
  name: "todolist",
  props: {
    list: {
      type: Object,
      required: true,
    },
  },
  methods: {
    deleteIteam() {
      this.$emit("delete", this.list.id);
    },
  },
};
</script>
<style>
.list {
  width: 100%;
  height: 100%;
  padding: 40px;
  background-color: #f5f5f5;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  align-content: center;
  list-style: none;
}
.list li {
  width: 70%;
  padding: 25px;
  border: 1px solid #ccc;
  display: flex;
  justify-content: space-between;
  align-items: center;
  box-shadow: 0 0 10px 10px #ccc;
  border-radius: 8px;
}
</style>
