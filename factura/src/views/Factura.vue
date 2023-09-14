<template>
  <main class="main">
    <section class="section1 width-50">
    <div class="form">
    <h1>Formulario</h1>
    <label>Articulo:</label>
    <br>
    <input type="text" v-model="articulo"> 
    <br>
    <label>Cantidad:</label>
    <br>
    <input type="text" v-model="cantidad"> 
    <br>
    <label>Valor unitario:</label>
    <br>
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
  background-color: lightblue;
  padding: 20px;
  height: 300px;
  width: 20vw;
}

.section2 {
  background-color: lightgreen;
  padding: 20px;
  height: 300px;
  width: 30vw;
  overflow-y: auto;

}


/* Estilo para las etiquetas */
label {
  font-weight: bold;
  margin-bottom: 5px;
}

/* Estilo para los inputs */
input {
  padding: 5px;
  width: 100%;
}

/* Estilo para el botón */
button {
  padding: 10px;
  margin: 15px;
  background-color: #007BFF;
  color: white;
  cursor: pointer;
}

button:hover {
  background-color: #0056b3;
}


</style>

