<!-- Author: Sebastian Aguirre Duque
E-mail: sadw621@gmail.com -->


<script>
export default {
  name: 'list-Exercise',
  data() {
    return {
      user: {
        username: 'Sebastian',
        role: 'author',
      },
      tasks: [
        { name: 'Aprender JavaScript moderno', time: 3 },
        { name: 'Aprender Vue.js', time: 7 },
        { name: 'Alistar el coche', time: 22 },
        { name: 'Viajar más', time: 15 },
        { name: 'Comprar la cena', time: 12 },
        { name: 'Mejorar como desarrollador', time: 9 },
        { name: 'Dar un curso', time: 14 },
      ],
      time: 0,
      search: 0,
    }
  },
  computed: {
    filterTask() {
      return this.tasks.filter(task => {
        return task.time <= this.time && task.name.includes(this.search);
      })
    },
  }
}
</script>

<template>
  <div class="app">
    <input v-model="time" type="range" name="time" id="">
    <br>
    <input v-model="search" type="search" name="name" id="" placeholder="Buscar tarea">
    <br>
    <p v-for="(key, value, index) in user" v-bind:key="index"> {{ value }} : {{ key }}</p>
    <br>
    <ul>
      <li v-for="(task, index) in filterTask" v-bind:key="index">{{ task.name }} - {{ task.time }}</li>
    </ul>
  </div>
</template>

