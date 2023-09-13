<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import factura from './views/Factura.vue'
import Tabla from './views/Tabla.vue'
</script>

<template>
  <main>
    <section>
      <factura></factura>
  
    </section>
  
    <section>
      <Tabla/>
  
    </section>

  </main>

  
  <RouterView />
</template>

<style scoped>
 main{
  display: flex;
 }
</style>
