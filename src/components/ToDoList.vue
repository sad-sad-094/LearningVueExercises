<!-- Author: Sebastian Aguirre Duque
E-mail: sadw621@gmail.com -->


<template>
  <div class="app">
    <form action="">
      <input type="text" name="value" id="value">
      <input type="submit" value="Guardar">

    </form>
    <hr>
    <ul>

    </ul>
  </div>
</template>

<script>

export default {
  name: 'toDo List',
  data: {
    newTask: '',
    tasks: [],

  },
  methods: {
    saveTask() {
      this.tasks.push(this.newTask)
    }
  }
}

</script>