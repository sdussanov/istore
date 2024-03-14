<template>
    <main>
        <Navbar />
        <Carousel />
        <ProductList :products="phones" />
        <ProductList :products="laptops" />
        <ProductList :products="ipads" />
        <Footer />
    </main>
</template>

<script>
import Navbar from '../components/Navbar.vue'
import Carousel from '../components/Carousel.vue'
import ProductList from '../components/ProductList.vue'
import Footer from '../components/Footer.vue'

export default {
    components: {
        Navbar,
        Carousel,
        ProductList,
        Footer
    },
    data() {
        return {
            phones: [
                {
                    name: 'iPhone 15 Pro Max',
                    description: 'Описание товара 1',
                    price: "729 990 ₸",
                    image: '../src/images/items/phone1.png',
                    link: 'phone1'
                },
                {
                    name: 'iPhone 15 Pro',
                    description: 'Описание товара 2',
                    price: "599 990 ₸",
                    image: '../src/images/items/phone2.png',
                    link: 'phone2'
                },
                {
                    name: 'iPhone 15',
                    description: 'Описание товара 3',
                    price: "449 990 ₸",
                    image: '../src/images/items/phone3.png',
                    link: 'phone3'
                },
                {
                    name: 'iPhone 14',
                    description: 'Описание товара 4',
                    price: "399 990 ₸",
                    image: '../src/images/items/phone4.png',
                    link: 'phone4'
                },
                {
                    name: 'iPhone 13',
                    description: 'Описание товара 5',
                    price: "334 990 ₸",
                    image: '../src/images/items/phone5.png',
                    link: 'phone5'
                }
            ],
            laptops: [
                {
                    name: 'MacBook Pro 16 Apple M3 Pro',
                    description: 'Описание товара 1',
                    price: "1 534 990 ₸",
                    image: '../src/images/items/mac1.png',
                    link: 'mac1'
                },
                {
                    name: 'MacBook Pro 16 Apple M1 Pro',
                    description: 'Описание товара 2',
                    price: "1 119 990 ₸",
                    image: '../src/images/items/mac2.png',
                    link: 'mac2'
                },
                {
                    name: 'MacBook Pro 14 Apple M1 Pro',
                    description: 'Описание товара 3',
                    price: "969 990 ₸",
                    image: '../src/images/items/mac3.png',
                    link: 'mac3'
                },
                {
                    name: 'MacBook Pro 13 Apple M2',
                    description: 'Описание товара 4',
                    price: "649 990 ₸",
                    image: '../src/images/items/mac4.png',
                    link: 'mac4'
                },
                {
                    name: 'MacBook Air 13 Apple M2',
                    description: 'Описание товара 5',
                    price: "589 990 ₸",
                    image: '../src/images/items/mac5.png',
                    link: 'mac5'
                }
            ],
            ipads: [
                {
                    name: 'iPad Pro 12.9',
                    description: 'Описание товара 1',
                    price: "699 990 ₸",
                    image: '../src/images/items/ipad1.png',
                    link: 'ipad1'
                },
                {
                    name: 'iPad Pro 11',
                    description: 'Описание товара 2',
                    price: "509 990 ₸",
                    image: '../src/images/items/ipad2.png',
                    link: 'ipad2'
                },
                {
                    name: 'iPad Air 5',
                    description: 'Описание товара 3',
                    price: "384 990 ₸",
                    image: '../src/images/items/ipad3.png',
                    link: 'ipad3'
                },
                {
                    name: 'iPad 10.2',
                    description: 'Описание товара 4',
                    price: "159 990 ₸",
                    image: '../src/images/items/ipad4.png',
                    link: 'ipad4'
                },
                {
                    name: 'iPad mini 6',
                    description: 'Описание товара 5',
                    price: "319 990 ₸",
                    image: '../src/images/items/ipad5.png',
                    link: 'ipad5'
                }
            ]
        }
    }
}
</script>
