<script setup>
import { ref } from 'vue'
import socksGreenImage from './assets/images/socks_green.jpeg'

const product = ref('Socks')
const image = ref(socksGreenImage)
const href = ref('https://www.vuemastery.com/courses/intro-to-vue-3-comp-api/attribute-binding-comp-api/')
</script>

<template>
  <div class="product-display">
    <div class="product-container">
      <div class="product-image">
        <!-- image goes here -->
        <!-- 讲属性绑定到表达式，约等于 <img v-bind:src="{{image}}" /> -->
         <img v-bind:src="image" />
         <!-- 或 -->
         <img :src="image" />
      </div>
      <div class="product-info">
        <h1>{{ product }}</h1>
        <a :href="href">learn</a>
      </div>
    </div>
  </div>
</template>