<script setup>
import { ref } from 'vue'

const cart = ref(0)
// import ProductDisplay from './components/ProductDisplay.vue'
import ProductDisplay from '@/components/ProductDisplay.vue'

const premium = ref(true)
</script>

<template>
  <div class="nav-bar"></div>
  <div class="cart">Cart({{ cart }})</div>
  <ProductDisplay :premium="premium"></ProductDisplay>
  <ProductDisplay></ProductDisplay>
  <product-display :premium="premium"></product-display>
</template>