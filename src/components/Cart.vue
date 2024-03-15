<template>
    <div class="container mt-4">
        <h2>Корзина</h2>
        <div v-if="cart.length === 0" class="alert alert-info" role="alert">
            Корзина пуста
        </div>
        <div v-else>
            <div v-for="(item, index) in cart" :key="index" class="card mb-4">
                <div class="row g-0">
                    <div class="col-md-4">
                        <img :src="item.image" class="img-fluid rounded-start" alt="Product Image">
                    </div>
                    <div class="col-md-7">
                        <div class="card-body">
                            <h5 class="card-title">{{ item.name }}</h5>
                            <p class="card-text">{{ item.description }}</p>
                            <p class="card-text">{{ item.fulldescription }}</p>
                            <p class="card-text"><strong>Цена: </strong>{{ item.price }}</p>
                            <button @click="removeFromCart(index)" class="btn btn-danger">Удалить из корзины</button>
                        </div>
                    </div>
                </div>
            </div>
            <div class="summary">
                <div class="total">
                    <p><strong>Общая сумма: </strong>{{ getTotalPrice() }}</p>
                </div>
                <div class="checkout-button">
                    <button @click="checkout" class="btn btn-success">Оформить заказ</button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            cart: []
        };
    },
    mounted() {
        this.loadCart();
    },
    methods: {
        loadCart() {
            const cartData = localStorage.getItem('cart');
            if (cartData) {
                this.cart = JSON.parse(cartData);
            }
        },
        removeFromCart(index) {
            this.cart.splice(index, 1);
            localStorage.setItem('cart', JSON.stringify(this.cart));
        },
        clearCart() {
            this.cart = [];
            localStorage.removeItem('cart');
        },
        getTotalPrice() {
            const totalPrice = this.cart.reduce((total, item) => total + parseFloat(item.amount), 0);
            return totalPrice.toLocaleString('kk-KZ', { style: 'currency', currency: 'KZT' });
        },
        checkout() {
            // Заготовка под кнопку оформить заказ
        }
    }
};
</script>

<style>
.summary {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-top: 20px;
}

.total {
    font-weight: bold;
}

.checkout-button {
    margin-left: auto;
}
</style>
