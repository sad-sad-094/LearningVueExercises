<!-- Author: Sebastian Aguirre Duque
E-mail: sadw621@gmail.com -->


<template>
  <div class='app'>
    <form>
      <label for="name">Nombre</label>
      <input type="text" name="name" id="" v-model="form.name">
      
      <label for="lastName">Apellidos</label>
      <input type="text" name="lastName" id="" v-model="form.lastName">
      
      <label for="message">Mensaje</label>
      <textarea name="messages" id="message" cols="40" rows="1" required v-model="form.message"></textarea>
      
      <label for="schedule">Horario de Contacto.</label>
      <span>Mañanas</span>
      <input v-model="form.contact" type="radio" name="mornings" id="">
      <span>Tardes</span>
      <input v-model="form.contact" type="radio" name="afternoons" id="">
      <span>Noches</span>
      <input v-model="form.contact" type="radio" name="evenings" id="">
      
      <select name="products" id="products" v-model="form.product">
        <option value="product1">Producto 1</option>
        <option value="product2">Producto 2</option>
        <option value="product3">Producto 3</option>
      </select>

      <label for="agreement">Acepta terminos y condiciones</label>
      <span>Acepto contrato</span>
      <input type="checkbox" name="agreement" id="" v-model="form.agree">

      <input type="submit" value="Enviar">
    </form>
  </div>
</template>

<script>
export default {
  name: 'FormsDataBinding',
  data() {
    return {
      form: {
        name: '',
        lastName: '',
        message: '',
        contact: '',
        product: '',
        agree: false,
      }
    }
  },
  methods: {

  },
  computed: {

  }
}
</script>

<!-- Add 'scoped' attribute to limit CSS to this component only -->
<style scoped>
</style>