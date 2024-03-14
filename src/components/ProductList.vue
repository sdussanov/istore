<template>
  <div class="container mt-4">
    <div class="row row-cols-2 row-cols-lg-5 g-2 g-lg-3">
      <div v-for="(product, index) in products" :key="index" class="col">
        <div class="card h-100">
          <img :src="product.image" class="card-img-top" alt="Product Image">
          <div class="card-body">
            <h5 class="card-title"><a href="#" class="product-link" @click.prevent="showDetails(product)">{{
        product.name }}</a></h5>
            <p class="card-text">{{ product.description }}</p>
            <div class="price-and-button">
              <span class="price">{{ product.price }}</span>
              <button @click="addToCart(product)" class="btn btn-primary">
                <span class="add">+</span>
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    products: {
      type: Array,
      required: true
    }
  },
  methods: {
    showDetails(product) {
      // тут будет действие на кнопку подробнее, заготовка
      console.log("Подробнее о товаре", product);
    },
    addToCart(product) {
      let cart = localStorage.getItem('cart');
      if (!cart) {
        cart = [];
      } else {
        cart = JSON.parse(cart);
      }
      cart.push(product);
      localStorage.setItem('cart', JSON.stringify(cart));
      console.log("Добавлено в корзину", product);
    }
  }
}
</script>

<style>
.product-link {
  color: black;
  text-decoration: none;
}

.product-link:hover {
  color: blue;
}

.btn-primary {
  background-color: black !important;
  border-color: black !important;
}

.btn-primary:hover {
  background-color: white !important;
  border-color: black !important;
}

.btn-primary:hover .add {
  color: black !important;
}

.price-and-button {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.price {
  margin-left: 10px;
  font-size: 25px;
  font-weight: bold;
  color: black;
}
</style>