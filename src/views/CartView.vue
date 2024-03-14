<template>
    <main>
        <Navbar />
        <Cart />
        <Footer />
    </main>
</template>

<script>
import Navbar from '../components/Navbar.vue'
import Cart from '../components/Cart.vue'
import Footer from '../components/Footer.vue'

export default {
    components: {
        Navbar,
        Cart,
        Footer
    }
}
</script>

<style></style>