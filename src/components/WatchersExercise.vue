<!-- Author: Sebastian Aguirre Duque
E-mail: sadw621@gmail.com -->


<template>
  <div class='app'>
    <h3>Cambiar contraseña</h3>
    <input type="text" name="password" id="" v-model="password">
    <br>
    <p>{{ state }}</p>
  </div>
</template>

<script>
export default {
  name: 'watcherExercise',
  data() {
    return {
      password: null,
      state: 'Write a new password',
      invalidPassword: [
        'admin',
        '12345',
        'password',
      ]
    }
  },
  methods: {

  },
  computed: {

  },
  watch: {
    password(newPass) {
      if (this.invalidPassword.indexOf(newPass) > -1) {
        this.state = 'Contraseña no válida';
        return false
      }

      if (newPass.length < 5) {
        this.state = 'Contraseña debe contener almenos 5 caracteres';
        return false
      }
      
      this.state = 'Contraseña correcta';
    }
  }
}
</script>


