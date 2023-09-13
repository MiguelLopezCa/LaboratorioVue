<template>
    <table class="tab">
      <thead>
        <tr>
          <th>#</th>
          <th>Articulo</th>
          <th>Cantidad</th>
          <th>V.Unit</th>
          <th>Total</th>
          <th>Eliminar</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(i, index) of articulos" :key="index">
          <td>{{ index + 1 }}</td>
          <td>{{ i.articulo }}</td>
          <td>{{ i.cantidad }}</td>
          <td>{{ i.valorUnitario }}</td>
        </tr>
      </tbody>
    </table>
  </template>
  
  <script lang="ts">

  export default {
    props: {
        articulos:Array
    },
    
  };
  </script>
  