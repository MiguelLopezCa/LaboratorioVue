<template>
  <section class="pu">
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
      <tbody class="tab contenido">
        <tr v-for="(item, index) of articulos" :key="index">
          <td>{{ index + 1 }}</td>
          <td>{{ item.articulo }}</td>
          <td>{{ item.cantidad }}</td>
          <td>{{ item.valorUnitario }}</td>
          <td>{{ item.cantidad * item.valorUnitario }}</td>
          <td>
            <img
              id="eliminar"
              src="../assets/eliminar.png"
              alt="Eliminar"
              class="icono-eliminar"
              @click="eliminarArticulo(index)"
            />
          </td>
        </tr>
      </tbody>
    </table>
  </section>
  <section>
    <h2>Total de Compras: {{ totalCompras }}</h2>
    <h2>Descuento: {{ descuento }}</h2>
    <h2>Descuento: {{ impDes }}</h2>
    <h2>Total de pagar: {{ total }}</h2>
  </section>
    
</template>

<script lang="ts">
export default {
  mounted() {
    this.calcularTotal(); 
  },

  data() {
    return {
      totalCompras: 0,
      descuento:0,
      total:0,
      impDes:''
    };
  },
  props: {
    articulos: Array,
  },
  watch: {
    articulos: {
      handler: 'calcularTotal', 
      deep: true, 
    },
  },

  methods: {
    eliminarArticulo(index) {
      this.articulos.splice(index, 1);
      this.calcularTotal();
    },
    calcularTotal() {
      let totalCompra = 0;
      let descuento=0;
      let impDes="";
      for (let i = 0; i < this.articulos.length; i++) {
        totalCompra += this.articulos[i].cantidad * this.articulos[i].valorUnitario; 
        if (i >= 5 ){
          descuento= (totalCompra*0.10)
          impDes="10%"
        }
        if(i >= 11 ){
          descuento= (totalCompra*0.20)
          impDes="20%"
      }
    }
      this.totalCompras = totalCompra;
      this.descuento= descuento;
      this.impDes= impDes;
    },
  },
};
</script>

<style>
.pu{
  height: 300px;
  width: 50vw;
  overflow-y: auto;
}
.tab {
  border: solid;
  color: black;
}
.tab .contenido {
  border: solid;
  color: black;
  text-align: center;
}

#eliminar {
  width: 25px;
}
</style>
