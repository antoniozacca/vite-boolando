<script>
import headers from './components/headerApp.vue'
import productsData from './db.json/db.json'
  export default {
    name: "myApp",
    components: {
      headers,
    },
    data(){
      return {
        products: productsData.products
      }
    }

}



</script>

<template>
  <headers></headers>
  <main>
    <div class="container">
      <div class="row">
        <div>

          <ul class="d-flex">
            <li class="card" v-for="product in products" :key="product.id">
              <img :src="product.frontImage" alt="">
              <h3>{{ product.brand }}</h3>
              <h3>{{ product.name }}</h3>
              <h3>{{ product.price }}</h3>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
  .container{
    padding-top: 100px;
    width: 100%;
    margin: 0 auto;
  }
  .row{
    display: flex;
    flex-wrap: wrap;
  }
  .card{
    margin: 10px;
    width: calc(100%/3 - 20px);
  }
  img{
    width: 100%;
  }
  .d-flex{
    display: flex;
  }
</style>
