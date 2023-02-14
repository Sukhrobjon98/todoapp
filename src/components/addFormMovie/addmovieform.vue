<template>
  <ul>
    <li class="list list-group">
      <span>Add New Task</span>
      <button class="btn btn-gray" @click="sendBoolen">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="16"
          height="16"
          fill="currentColor"
          class="bi bi-plus-circle"
          viewBox="0 0 16 16">
          <path
            d="M8 15A7 7 0 1 1 8 1a7 7 0 0 1 0 14zm0 1A8 8 0 1 0 8 0a8 8 0 0 0 0 16z" />
          <path
            d="M8 4a.5.5 0 0 1 .5.5v3h3a.5.5 0 0 1 0 1h-3v3a.5.5 0 0 1-1 0v-3h-3a.5.5 0 0 1 0-1h3v-3A.5.5 0 0 1 8 4z" />
        </svg>
      </button>
    </li>
  </ul>
</template>
<script lang="ts">
export default {
  name: "addmovieform",
  data() {
    return {
      isPressed: false,
    };
  },
  methods: {
    sendBoolen() {
      this.$emit("sendBoolen", !this.isPressed);
    },
  },
};
</script>
<style>
.btn:hover {
  background-color: gray;
  border: none;
  outline: none;
  cursor: pointer;
}
.btn {
  background-color: rgb(200, 193, 193);
  border: none;
  outline: none;
  cursor: pointer;
}
.list {
  margin: 0;
  padding: 0;
  background-color: rgb(221, 217, 217);
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  box-shadow: 0 0 5px 3px rgba(0, 0, 0, 0.4);
  width: 150%;
}
</style>
