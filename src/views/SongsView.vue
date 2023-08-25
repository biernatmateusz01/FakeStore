<template>
  <DefaultLayout>
    <template #filters>
      <BaseFilters @change-filter="changeFilter($event)" :filters="categories" />
    </template>
    <template #elements>
      <SongContainer>
        <SongItem  v-for="(product, index) in products" :key="index" :product="product" @buy-product="addToCart()"/>
      </SongContainer>
    </template>
  </DefaultLayout>
</template>

<script setup>
import { onMounted, ref } from 'vue'
import DefaultLayout from '../components/DefaultLayout.vue'
import SongContainer from '../components/SongContainer.vue'
import SongItem from '../components/SongItem.vue'
import BaseFilters from '../components/BaseFilters.vue'

let products = ref([])
let categories = ref([]);


const addToCart = () => {
  alert(`w tej chwili dodanie produktu do koszyka jest niemozliwe`)
}

const getProducts = async () => {
  try {
    const response = await fetch('https://fakestoreapi.com/products')
    const data = await response.json()
    products.value = data
  } catch (error) {
    console.error('Error fetching data:', error)
  }
}


const changeFilter = async (el) => {
    try {
    const response = await fetch(`https://fakestoreapi.com/products/category/${el}`)
    const data = await response.json()
    products.value = data
  } catch (error) {
    console.error('Error fetching data:', error)
  }

  if(products.value.length === 0){
    getProducts()
  }
}

const getCategories = async () => {
  try {
    const response = await fetch('https://fakestoreapi.com/products/categories');
    const data = await response.json();
    categories.value = data;
  } catch (error) {
    console.error('Error fetching data:', error);
  }
};

onMounted(() => {
  getProducts()
  getCategories();

})
</script>
