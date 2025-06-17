<script setup>
import { ref } from 'vue'
import socksGreenImage from './assets/images/socks_green.jpeg'
import socksBlueImage from './assets/images/socks_blue.jpeg'

const product = ref('Socks')
const image = ref(socksGreenImage)
const inStock = false

const details = ref(['50% cotton', '30% wool', '20% polyester'])

const variants = ref([
  { id: 2234, color: 'green', image: socksGreenImage },
  { id: 2235, color: 'blue', image: socksBlueImage },
])

const cart = ref(0)

const addToCart = () => cart.value += 1

const updateImage = (variantImage) => image.value = variantImage

const color = 'red'
const fontSize = '16px'

import { reactive } from 'vue'
const styles = reactive({
  color,
  fontSize
})

const activeClass = true

const inActive = true

</script>

<template>
  <div class="nav-bar"></div>
  <div class="cart">Cart({{ cart }})</div>
  <div class="product-display">
    <div class="product-container">
      <div class="product-image">
        <img v-bind:src="image" :class="{ 'out-of-stock-img': !inStock }">
      </div>
      <div class="product-info">
        <h1>{{ product }}</h1>
        <p v-if="inStock">In Stock</p>
        <p v-else>Out of Stock</p>
        <ul>
          <li v-for="detail in details">{{ detail }}</li>
        </ul>
        <!-- 
        在这个表达式中，请记住这个样式对象完全是 JavaScript。
        这就是为什么我在属性名中使用了驼峰命名法。
        如果我写的是 background-color，那会被解释为一个减号。
        除非我们想在引号中使用“kebab-cased”以避免数学上的误解。
         -->
        <div v-for="variant in variants" :key="variant.id" @mouseover="updateImage(variant.image)" class="color-circle"
          :class="{ active: activeClass }" :style="{ backgroundColor: variant.color }">
        </div>
        <button class="button" :class="{ disabledButton: !inStock }" :disabled="!inStock" v-on:click="addToCart">Add to
          cart</button>
        <div :style="styles">123</div>
        <!-- 
        在JavaScript中，逗号操作符会依次执行表达式，但只返回最后一个值
        Vue期望的数据类型：:class 期望接收字符串、对象或数组，不是逗号表达式
        ❌ 错误语法
        <div :class="isActive ? activeClass : '', isActive ? activeClass : ''"></div>
        -->
        <div :class="[isActive ? activeClass : '']"></div>
      </div>
    </div>
  </div>
</template>