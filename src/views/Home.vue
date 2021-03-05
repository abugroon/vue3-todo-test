<template>
  <div class="container">
    <!-- <img alt="Vue logo" src="../assets/logo.png" /> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
    <h1 class="text-primary">Todo List</h1>
    <div class="row mt-2">
      <div
        class="col-md-6 col-sm-12 mb-2 col-lg-4 d-flex align-items-stretch "
        :key="todo.id"
        v-for="(todo, index) in todos.splice(0, 12)"
      >
        <div class="card w-100 ">
          <div class="card-body">
            <h5 class="card-text">{{ index + 1 }} / {{ todo.title }}</h5>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import { ref } from "vue";
export default {
  setup() {
    let todos = ref([]);
    const loadData = () => {
      fetch("https://jsonplaceholder.typicode.com/todos")
        .then((response) => response.json())
        .then((json) => (todos.value = json));
    };
    loadData();
    return {
      HelloWorld,
      todos,
    };
  },
};
</script>
