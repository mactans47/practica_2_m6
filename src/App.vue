<template>
  <MenuLateral/>
  <Producto/>
  <ProductosRelacionados/>
  <PiePagina/>
</template>

<script>
import MenuLateral from './components/MenuLateral.vue'
import Producto from './components/Producto.vue'
import ProductosRelacionados from './components/ProductosRelacionados.vue'
import PiePagina from './components/PiePagina.vue'

export default {
  name: 'App',
  components: {
    MenuLateral,
    Producto,
    ProductosRelacionados,
    PiePagina
  }
}
</script>


