<!-- Author: Sebastian Aguirre Duque
E-mail: sadw621@gmail.com -->


<template>
  <div class='app'>
    <span>Log-in/out</span>
    <input type="checkbox" name="logged" id="" v-model="logged">
    <article class="user-info" :class="styles">
      {{ message }}
    </article>
  </div>
</template>

<script>
export default {
  name: 'StylesDataBindng',
  data() {
    return {
      logged: true,
      messages: {
        in: 'Logeado como aprendiz',
        out: 'Te has deslogueado',
      }
    }
  },
  methods: {

  },
  computed: {
    message() {
      return this.logged ? this.messages.in : this.messages.out;
    },
    styles() {
      return {
        'logged-in': this.logged,
        'logged-out': !this.logged,
      }
    }
  }
}
</script>

<!-- Add 'scoped' attribute to limit CSS to this component only -->
<style scoped>
.user-info {
  text-align: center;
  padding: 2rem;
  border: 1px solid;
  border-radius: 25px;
  font-family: sans-serif;
  color: #fff;
}
  .logged-in {
    background-color: rgb(65,184,131);
  }
  .logged-out {
    background-color: rgb(53,73,94);
  }
</style>