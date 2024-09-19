<template>
  <v-app class="app-background">
    <v-container class="main-container">
      <v-row justify="center">
        <v-col cols="12" class="text-center">
          <h1>To-Do List</h1>
        </v-col>
      </v-row>
      <TodoList />
    </v-container>
  </v-app>
</template>

<script>
import TodoList from './components/TodoList.vue';

export default {
  components: {
    TodoList,
  },
};
</script>

<style>
.app-background {
  background-color: #51bce0; /* Background color for the entire page */
  min-height: 100vh; /* Ensures it covers full viewport height */
  padding: 20px; /* Optional: padding around the content */
  background-image: url(assets/aaa.jpg);
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}
</style>
