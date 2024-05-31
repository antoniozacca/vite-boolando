<script>
import headers from './components/headerApp.vue'
import productsData from './db.json/db.json'

export default {
  name: "myApp",
  components: {
    headers,
  },
  data() {
    return {
      products: productsData.products
    }
  },
  computed: {
    discountedProducts() {
      return this.products.map(product => {
        let discountBadge = product.badges.find(badge => badge.type === 'discount');
        let discount = discountBadge ? parseFloat(discountBadge.value.replace('%', '').replace('-', '')) / 100 : 0;
        let discountedPrice = product.price * (1 - discount);
        return {
          ...product,
          discountedPrice: discountedPrice.toFixed(2)
        };
      });
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
            <li class="card " v-for="product in discountedProducts" :key="product.id">
                <img class="d-block" :src="product.frontImage" alt="">
                <img class="d-none" :src="product.backImage" alt="">
                <p>{{ product.brand }}</p>
                <h2>{{ product.name }}</h2>
                <span class="text-sold">{{ product.discountedPrice }} €</span>
                <span class="line-through">{{ product.price }} €</span>
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
    max-width: 1300px;
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
    flex-wrap: wrap;
  }
  .d-block{
    display: block;
  }
  .d-none{
    display: none;
  }
  .card:hover .d-block{
    display: none;
}
  .card:hover .d-none{
    display: block;
}
  .line-through{
    text-decoration: line-through;
  }
  .text-sold{
    color: red;
    font-weight: bold;
    padding-right: 10px;
  }
</style>
