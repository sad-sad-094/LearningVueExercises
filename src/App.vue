<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <!-- <ToDoList /> -->
  <!-- <ListsExercise /> -->
  <!-- <EventsExercise /> -->
  <WatchersExercise />
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue';
// import ToDoList from './components/ToDoList.vue';
// import ListsExercise from './components/ListsExercise.vue';
// import EventsExercise from './components/EventsExercise.vue';
import WatchersExercise from './components/WatchersExercise.vue';


export default {
  name: 'App',
  components: {
    // ToDoList,
    // ListsExercise,
    // EventsExercise,
    WatchersExercise
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
