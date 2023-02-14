<template>
  <form class="form-control form" @submit.prevent>
    <input type="text" placeholder="Ismingizni kirting..." v-model="name" />
    <input type="text" placeholder="Yilingizni kiring..." v-model="year" />
    <button @click="submit" type="button">Submit</button>
  </form>
</template>
<script lang="ts">
export default {
  name: "forma",
  methods: {
    submit() {
      const newData = {
        id: Date.now(),
        name: this.name,
        year: this.year,
      };
      this.$emit("submit", newData);
    },
  },
  data() {
    return {
      name: "",
      year: "",
    };
  },
};
</script>
<style>
.form {
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

.form input {
  width: 100%;
  height: 40px;
  margin: 10px;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.form button {
  width: 100%;
  height: 40px;
  margin: 10px;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
  color: black;
  font-weight: bold;
  cursor: pointer;
}
</style>
