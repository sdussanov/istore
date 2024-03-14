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
                    description: '256GB White',
                    fulldescription: 'Display has rounded corners that follow a beautiful curved design, and these corners are within a standard rectangle. When measured as a standard rectangular shape, the screen is 6.12 inches diagonally (actual viewable area is less).',
                    price: "729 990 ₸",
                    amount: 729990,
                    image: '../src/images/items/phone1.png'
                },
                {
                    name: 'iPhone 15 Pro',
                    description: '256GB Gray',
                    fulldescription: 'Display has rounded corners that follow a beautiful curved design, and these corners are within a standard rectangle. When measured as a standard rectangular shape, the screen is 6.12 inches diagonally (actual viewable area is less).',
                    price: "599 990 ₸",
                    amount: 599990,
                    image: '../src/images/items/phone2.png'
                },
                {
                    name: 'iPhone 15',
                    description: '256GB Pink',
                    fulldescription: 'Display has rounded corners that follow a beautiful curved design, and these corners are within a standard rectangle. When measured as a standard rectangular shape, the screen is 6.12 inches diagonally (actual viewable area is less).',
                    price: "449 990 ₸",
                    amount: 499990,
                    image: '../src/images/items/phone3.png'
                },
                {
                    name: 'iPhone 14',
                    description: '256GB Blue',
                    fulldescription: 'Display has rounded corners that follow a beautiful curved design, and these corners are within a standard rectangle. When measured as a standard rectangular shape, the screen is 6.12 inches diagonally (actual viewable area is less).',
                    price: "399 990 ₸",
                    image: '../src/images/items/phone4.png',
                    link: 'phone4'
                },
                {
                    name: 'iPhone 13',
                    description: '256GB White',
                    fulldescription: 'Display has rounded corners that follow a beautiful curved design, and these corners are within a standard rectangle. When measured as a standard rectangular shape, the screen is 6.12 inches diagonally (actual viewable area is less).',
                    price: "334 990 ₸",
                    amount: 334990,
                    image: '../src/images/items/phone5.png',
                    link: 'phone5'
                }
            ],
            laptops: [
                {
                    name: 'MacBook Pro 16 Apple M3 Pro',
                    description: '1TB SSD 16"',
                    fulldescription: 'Display has rounded corners that follow a beautiful curved design, and these corners are within a standard rectangle. When measured as a standard rectangular shape, the screen is 6.12 inches diagonally (actual viewable area is less).',
                    price: "1 534 990 ₸",
                    amount: 1534990,
                    image: '../src/images/items/mac1.png'
                },
                {
                    name: 'MacBook Pro 16 Apple M1 Pro',
                    description: '1TB SSD 16"',
                    fulldescription: 'Display has rounded corners that follow a beautiful curved design, and these corners are within a standard rectangle. When measured as a standard rectangular shape, the screen is 6.12 inches diagonally (actual viewable area is less).',
                    price: "1 119 990 ₸",
                    amount: 1119990,
                    image: '../src/images/items/mac2.png'
                },
                {
                    name: 'MacBook Pro 14 Apple M1 Pro',
                    description: '1TB SSD 16"',
                    fulldescription: 'Display has rounded corners that follow a beautiful curved design, and these corners are within a standard rectangle. When measured as a standard rectangular shape, the screen is 6.12 inches diagonally (actual viewable area is less).',
                    price: "969 990 ₸",
                    amount: 969990,
                    image: '../src/images/items/mac3.png'
                },
                {
                    name: 'MacBook Pro 13 Apple M2',
                    description: '1TB SSD 16"',
                    fulldescription: 'Display has rounded corners that follow a beautiful curved design, and these corners are within a standard rectangle. When measured as a standard rectangular shape, the screen is 6.12 inches diagonally (actual viewable area is less).',
                    price: "649 990 ₸",
                    amount: 649990,
                    image: '../src/images/items/mac4.png'
                },
                {
                    name: 'MacBook Air 13 Apple M2',
                    description: '1TB SSD 13"',
                    fulldescription: 'Display has rounded corners that follow a beautiful curved design, and these corners are within a standard rectangle. When measured as a standard rectangular shape, the screen is 6.12 inches diagonally (actual viewable area is less).',
                    price: "589 990 ₸",
                    amount: 589990,
                    image: '../src/images/items/mac5.png'
                }
            ],
            ipads: [
                {
                    name: 'iPad Pro 12.9',
                    description: '512GB Grey',
                    fulldescription: 'Display has rounded corners that follow a beautiful curved design, and these corners are within a standard rectangle. When measured as a standard rectangular shape, the screen is 6.12 inches diagonally (actual viewable area is less).',
                    price: "699 990 ₸",
                    amount: 699990,
                    image: '../src/images/items/ipad1.png'
                },
                {
                    name: 'iPad Pro 11',
                    description: '512GB White',
                    fulldescription: 'Display has rounded corners that follow a beautiful curved design, and these corners are within a standard rectangle. When measured as a standard rectangular shape, the screen is 6.12 inches diagonally (actual viewable area is less).',
                    price: "509 990 ₸",
                    amount: 509990,
                    image: '../src/images/items/ipad2.png'
                },
                {
                    name: 'iPad Air 5',
                    description: '512GB Grey',
                    fulldescription: 'Display has rounded corners that follow a beautiful curved design, and these corners are within a standard rectangle. When measured as a standard rectangular shape, the screen is 6.12 inches diagonally (actual viewable area is less).',
                    price: "384 990 ₸",
                    amount: 384990,
                    image: '../src/images/items/ipad3.png'
                },
                {
                    name: 'iPad 10.2',
                    description: '512GB Grey',
                    fulldescription: 'Display has rounded corners that follow a beautiful curved design, and these corners are within a standard rectangle. When measured as a standard rectangular shape, the screen is 6.12 inches diagonally (actual viewable area is less).',
                    price: "159 990 ₸",
                    amount: 159990,
                    image: '../src/images/items/ipad4.png'
                },
                {
                    name: 'iPad mini 6',
                    description: '512GB Grey',
                    fulldescription: 'Display has rounded corners that follow a beautiful curved design, and these corners are within a standard rectangle. When measured as a standard rectangular shape, the screen is 6.12 inches diagonally (actual viewable area is less).',
                    price: "319 990 ₸",
                    amount: 319990,
                    image: '../src/images/items/ipad5.png'
                }
            ]
        }
    }
}
</script>
