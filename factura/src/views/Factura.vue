<template>
  <main class="main">
    <section class="section1 width-50">
    <div class="form">
      <h1>Formulario</h1>
      <label>Articulo:</label>
      <input type="text" v-model="articulo"> 
      <label>Cantidad:</label>
      <input type="text" v-model="cantidad"> 
      <label>Valor unitario:</label>
      <input type="text" v-model="valorUnitario">
     <button @click="agregar">Agregar</button> 
  </div>
  </section>
  <section class="section2">
    <Tabla :articulos="articulos"></Tabla>
  </section>
  </main>
  
</template>

<script lang="ts">
import Tabla from './Tabla.vue';
export default {
  data() {
    return {
      articulo: '',
      cantidad: '',
      valorUnitario: '',
      articulos: []
    };
  },
  components: { Tabla },
  methods: {
    agregar() {
      // Crear un nuevo objeto con los datos ingresados
      const nuevoArticulo = {
        articulo: this.articulo,
        cantidad: this.cantidad,
        valorUnitario: this.valorUnitario
      };

      // Agregar el nuevo objeto a la lista de articulos
      this.articulos.push(nuevoArticulo);

      // Limpiar los campos después de agregar
      this.articulo = '';
      this.cantidad = '';
      this.valorUnitario = '';
    }
  }
};
</script>
<style scoped>
.main{
  display: grid;
  grid-template-areas: "section1 section2"
}

.section1 {
  padding: 20px;
  height:300px; 
  width: 20vw;
}

.section2 {
  padding: 20px;
  height: 300px;
  width: 30vw;
  

}
.form{
margin: 2%;
border-radius: 5px;
border: 1px solid;
background-color: lightblue;
}
h1{
text-align: center;}
label {
  font-weight: bold;
  margin-bottom: 5px;
}

input {
  padding: 5px;
  margin: 5px;
  width: 90%;
}

button {
display: block;
  padding: 10px;
  margin: 15px;
  background-color: #007BFF;
  color: white;
  cursor: pointer;
  border-radius: 8%;


}

button:hover {
  background-color: #0056b3;
}


</style>

