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
    <div class="modal" :class="{ 'is-active': showModal }">
        <div class="modal-background" @click="showModal = false"></div>
        <div class="modal-content">
            <div class="box modal-product-info">
                <img :src="selectedProduct.image" class="modal-product-image" alt="Product Image">
                <div class="modal-product-details">

                    <div class="card-body">
                        <h5 class="card-title"><b>{{ selectedProduct.name }}</b></h5>
                        <p class="card-text">{{ selectedProduct.description }}</p>
                        <div class="color-options">
                            <span class="color-option" style="background-color: #D3D3D3;"></span>
                            <span class="color-option" style="background-color: #C0C0C0;"></span>
                            <span class="color-option" style="background-color: #FFD700;"></span>
                            <span class="color-option" style="background-color: #FFC0CB;"></span>
                        </div>
                        <div class="price-and-button">
                            <span class="price">{{ selectedProduct.price }}</span>
                            <button @click="addToCart(selectedProduct)" class="btn btn-primary">Добавить в
                                корзину</button>
                        </div>
                    </div><br>
                    <p>{{ selectedProduct.fulldescription }}</p>
                </div>
            </div>
        </div>
        <button class="modal-close is-large" aria-label="close" @click="showModal = false"></button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            showModal: false,
            selectedProduct: { name: '', description: '', price: '' }
        };
    },
    props: {
        products: {
            type: Array,
            required: true
        }
    },
    methods: {
        showDetails(product) {
            this.selectedProduct = product;
            this.showModal = true;
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

.modal {
    display: none;
    position: relative;
    top: 0;
    left: 0;
    width: 60%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
}

.modal.is-active {
    display: flex;
    justify-content: center;
    align-items: center;
}

.modal-background {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}

.modal-content {
    max-width: 800px;
    background-color: white;
    padding: 20px;
}

.modal-product-info {
    display: grid;
    grid-template-columns: auto 1fr;
    grid-column-gap: 20px;
    align-items: center;
}

.modal-product-image {
    max-width: 100%;
}

.modal-product-details {
    display: flex;
    flex-direction: column;
}

.modal-close {
    position: absolute;
    top: 15px;
    right: 15px;
    background-color: transparent;
    border: none;
    cursor: pointer;
}

.color-options {
  display: flex;
  gap: 5px;
}

.color-option {
  width: 30px;
  height: 30px;
  border: 1px solid black;
  cursor: pointer;
}
</style>