<template>
  <v-container class="background">
    <v-row>
      <v-col>
        <v-text-field
          v-model="newTask"
          label="Add a new task"
          @keyup.enter="addTask"
          class="mb-2"
          outlined
          color="white"
        ></v-text-field>
        <v-btn @click="addTask" color="primary" class="mb-3">Add task</v-btn>
      </v-col>
    </v-row>

    <v-list>
      <v-list-item-group>
        <v-list-item
          v-for="(task, index) in tasks"
          :key="index"
          class="task-item"
        >
          <v-list-item-content class="d-flex justify-space-between align-center">
            <v-list-item-title class="task-text">{{ task }}</v-list-item-title>
            <v-list-item-action>
              <v-btn icon @click="removeTask(index)" color="red">
                <v-icon>mdi-delete</v-icon>
              </v-btn>
            </v-list-item-action>
          </v-list-item-content>
        </v-list-item>
      </v-list-item-group>
    </v-list>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      newTask: '',
      tasks: []
    };
  },
  methods: {
    addTask() {
      if (this.newTask.trim() === '') return;
      this.tasks.push(this.newTask);
      this.newTask = '';
    },
    removeTask(index) {
      this.tasks.splice(index, 1);
    }
  }
};
</script>

<style scoped>
.background {
  background-color: #000000; /* Black background */
  padding: 20px; /* Padding around the container */
  border-radius: 8px; /* Rounded corners */
  color: rgb(248, 245, 245); /* Default text color */
}

.task-text {
  color: white; /* Ensures task text is white */
}

.task-item {
  background-color: rgb(2, 5, 5); /* Background for each task */
  border-radius: 4px; /* Rounded corners for task items */
   /* Padding inside each task */
}
</style>
