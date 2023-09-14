
<template>
  <h1>
  </h1>
  <table class="tab">
    <thead class="tab">
      <tr>
        <th>#</th>
        <th>Articulo</th>
        <th>Cantidad</th>
        <th>V.Unit</th>
        <th>Total</th>
        <th>Eliminar</th>
      </tr>
    </thead>
    <tbody class="tab">
      <tr v-for="(i, index) of articulos" :key="index">
        <td>{{ index + 1 }}</td>
        <td>{{ i.articulo }}</td>
        <td>{{ i.cantidad }}</td>
        <td>{{ i.valorUnitario }}</td>
        <td>{{ i.cantidad * i.valorUnitario }}</td>
        <td>
          <button @click="eliminarArticulo(index)">Eliminar</button>
        </td>
      </tr>
    </tbody>
  </table>
</template>
<script lang="ts">
export default {
  props: {
    articulos: Array,
  },
  methods: {
    eliminarArticulo(index) {
      // Eliminar el artículo de la lista de artículos
      this.articulos.splice(index, 1);
    },
  },
};
</script>

<style>
.tab{
  border: solid;
  color: black;

}
</style>