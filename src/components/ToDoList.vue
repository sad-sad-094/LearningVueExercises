<!-- Author: Sebastian Aguirre Duque
E-mail: sadw621@gmail.com -->


<script>
export default {
  name: 'toDo List',
  data() {
    return {
      newTask: '',
      tasks: [
        'Aprender Vue', 'Aprender Pinia'
      ],
    }

  },
  methods: {
    saveTask() {
      this.tasks.push(this.newTask);
      this.newTask = '';
    }
  },
  computed: {

  },
}

</script>

<template>
  <div class="app">
    <form action="" v-on:submit.prevent="saveTask">
      <input v-model="newTask" type="text" name="value" id="value">
      <input type="submit" value="Guardar">
    </form>
    <hr>
    <ul>
      <li v-for="(task, index) in tasks" v-bind:key="index" id="task">
        {{ task }} Hola
      </li>
    </ul>
  </div>
</template>
      



