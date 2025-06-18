<script setup>
import { ref } from 'vue'
import ProductDisplay from '@/components/ProductDisplay.vue'

// const cart = ref(0)
const cart = ref([])
const premium = ref(true)

const updateCart = (id) => {
  cart.value.push(id)
}

const removeFromCart = (id) => {
  const index = cart.value.findIndex(item => item === id)
  if (index === -1) return // 如果没有找到，直接返回
  cart.value.splice(index, 1)
}

// splice，当没有匹配项时会返回 -1，将移除最后一个元素
// const removeFromCart = (id) => {
//   cart.value.splice(cart.value.indexOf(id), 1)
// }

// 会移除全部相同id的商品 
// const removeFromCart = (id) => {
//   cart.value = cart.value.filter((item) => item !== id)
// }
</script>

<template>
  <div class="nav-bar"></div>
  <div class="cart">Cart({{ cart }})</div>
  <div class="cart">Cart({{ cart.length }})</div>
  <ProductDisplay :premium="premium" @add-to-cart="updateCart" @remove-from-cart="removeFromCart"></ProductDisplay>
</template>