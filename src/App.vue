<script>
import headers from './components/headerApp.vue'
import mains from './components/mainApp.vue'
import productsData from './db.json/db.json'
  export default {
    name: "myApp",
    components: {
      headers,
      mains,
      productsData
    },

}



</script>

<template>
  <headers></headers>
  <mains class="mains">
    <ul>
      <li v-for="product in products" :key="product.id">
        <img :src="product.frontImage" alt="">
        <h3>{{ product.brand }}</h3>
        <h3>{{ product.name }}</h3>
        <h3>{{ product.price }}</h3>
      </li>
    </ul>
  </mains>
</template>

<style scoped>
.mains{
  margin-top: 40px;
}
</style>
