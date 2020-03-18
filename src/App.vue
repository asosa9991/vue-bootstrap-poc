<template>
  <div>
    <Header />
    <div id="app">
      <Todos :todos="todos" />
    </div>
  </div>
</template>

<script>
import Todos from "./components/ToDos.vue";
import axios from "axios";
import Header from "./components/Header.vue";

export default {
  name: "App",
  components: {
    Todos,
    Header
  },
  data() {
    return { todos: [] };
  },
  created() {
    axios
      .get("https://jsonplaceholder.typicode.com/todos")
      .then(resp => (this.todos = resp.data))
      .catch(error => console.log(error));
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  /* -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale; */
  /* text-align: center; */
  /* color: #2c3e50; */
  /* margin: 160px; */
}
</style>
