<!-- Author: Sebastian Aguirre Duque
E-mail: sadw621@gmail.com -->


<template>
  <div class='app'>
    <ul>
      <li v-for="(user, index) in fullName" :key="index">{{ user }}</li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'FiltersExercise',
  data() {
    return {
      url: 'https://randomuser.me/api/?results=50',
      users: [],
    }
  },
  methods: {

  },
  computed: {
    fullName() {
      return this.users.map(user => `Nombre: ${user.name.title}. ${user.name.first} ${user.name.last}`);
    },
    capitalCase() {
      return this.users.map(element => element.name.toUpperCase());
    }
  },
  // filters: {
  //   capitalCase(data) {
  //     return data.toUpperCase();
  //   }
  // },
  mounted() {
    axios.get(this.url)
      .then(resp => this.users = resp.data.results);
  }
}
</script>

<!-- Add 'scoped' attribute to limit CSS to this component only -->
<style scoped></style>

