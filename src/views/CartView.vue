<template>
<div>
    Koszyk tu bedzie
</div>
</template>

<script setup>
import { onMounted, ref } from 'vue'
import DefaultLayout from '../components/DefaultLayout.vue'

const cartItems = [
  {
    title: 'Produkt 1',
    description: 'Opis produktu 1',
    image: 'https://example.com/product1.jpg',
    price: 50,
  },
  {
    title: 'Produkt 2',
    description: 'Opis produktu 2',
    image: 'https://example.com/product2.jpg',
    price: 30,
  },
];

const total = cartItems.reduce((acc, item) => acc + item.price, 0);

const removeItem = (index) => {
  cartItems.splice(index, 1);
};
</script>
