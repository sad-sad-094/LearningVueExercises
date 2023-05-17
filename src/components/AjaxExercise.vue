<!-- Author: Sebastian Aguirre Duque
E-mail: sadw621@gmail.com -->

<template>
  <div class='app'>
    <form @submit.prevent="saveTask">
      <input v-model="newTask" type="text" name="task" id="" placeholder="Tarea" required>
      <input type="submit" value="Enviar">
    </form>
    <ul>
      <li v-for="(task, index) in tasks" :key="index">{{ task.title }}</li>
    </ul>
    <pre>{{ tasks }}</pre>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'AxiosAjax',
  data() {
    return {
      url: 'https://jsonplaceholder.typicode.com/todos',
      newTask: '',
      tasks: []
    }
  },
  methods: {
    saveTask() {
      axios.post(this.url, {
        title: this.newTask,
        userId: Math.floor(Math.random() * 10) + 1
      })
        .then(response => {
          console.log(response);
          this.tasks.unshift({
            title: this.newTask,
          })
          this.newTask = '';
        })
        .catch(error => console.error(error));
    }
  },
  computed: {

  },
  mounted() {
    axios.get(this.url)
      .then(response => this.tasks = response.data)
      .catch(error => console.error(error));
  }
}
</script>

<!-- Add 'scoped' attribute to limit CSS to this component only -->
<style scoped></style>