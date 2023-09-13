<template>
    <div class="form">
        
        <h1>Formulario</h1>
        <label>Articulo:</label>
        <br>

        <input type="text">
        <br>
        <label>Cantidad:</label>
        <br>

        <input type="text">
        <br>

        <label>Valor unitario:</label>
        <br>
        <input type="text">
        <br>
      <button @click="agregar">Agregar</button>
    </div>
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
        const nuevoArticulos = {
          articulo: this.articulo,
          cantidad: this.cantidad,
          valorUnitario: this.valorUnitario
        };
      }
    }
  };
  </script>
  