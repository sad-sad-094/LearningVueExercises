<!-- Author: Sebastian Aguirre Duque
E-mail: sadw621@gmail.com -->


<template>
  <div class='app'>
    <form v-on:submit.prevent="saveData">

      <label for="name">Nombre</label>
      <input type="text" name="name" id="name" placeholder="Introduzca su nombre" v-model="name">
      <label for="lastName">Apellidos</label>
      <input type="text" name="lastName" id="lastName" placeholder="Introduzca sus apellidos" v-model="lastName">

      <label for="adress">Dirección de envíos</label>
      <select name="adress" id="adress" v-model="paymentAdress">
        <option value="sameAdress">Misma dirección de facturación</option>
        <option value="newAdress">Introducir nueva dirección</option>
      </select>

      <template v-if="paymentAdress === 'newAdress'">
        <label for="newAdress">Nueva Dirección</label>
        <textarea name="newAdress" id="newAdress" cols="40" rows="1" v-model="adress"></textarea>
      </template>

      <div>
        <input v-model="check" type="checkbox" name="terms" id="terms"><span>He leído y acepto la política de
          privacidad</span>
      </div>

      <input className="botton" v-if="check" type="submit" value="Enviar">
      <p v-else>Acepta política de privacidad para enviar formulario</p>

    </form>
  </div>
</template>

<script>
export default {
  name: 'ConditionalRender',
  data() {
    return {
      name: '',
      lastName: '',
      adress: '',
      paymentAdress: '',
      check: false,
      data: {},
    }
  },
  methods: {
    checked() {
      return this.check = true;
    },
    adrees() {
      this.paymentAdress = this.newAdress;
    },
    saveData() {
      this.data = {
        name: this.name,
        lastName: this.lastName,
        adress: this.adress,
        paymentAdress: this.paymentAdress,
      };
    }
  },
  computed: {

  }
}
</script>

<!-- Add 'scoped' attribute to limit CSS to this component only -->
<style scoped>
.app {
  display: flex;
  align-items: center;
  justify-content: center;
}

form {
  width: 30%;
  display: flex;
  flex-direction: column;
  gap: .5rem;
  padding: 1rem;
  border: 3px solid rgb(65, 184, 131);
  border-radius: 15px;
}

label {
  font-size: 1rem;
  color: rgb(65, 184, 131);
  font-weight: bold;
}

p {
  font-size: .8rem;
  color: rgb(53, 73, 94);
  font-weight: bold;
}

input {
  border: 2px solid rgb(65, 184, 131);
  color: rgb(53,73,94);
}

textarea {
  border: 2px solid rgb(65, 184, 131);
}

.botton {
  width: 50%;
  background-color: rgb(65,184,131);
  color: white;
  font-weight: bold;
  border-radius: 7px;
  align-self: center;
}
</style>

