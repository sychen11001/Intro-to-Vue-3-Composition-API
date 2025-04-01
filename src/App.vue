<script setup>
import { ref } from 'vue'

const product = ref('Socks')

</script>

<template>
  <div class="product-display">
    <div class="product-container">
      <div class="product-image">
        <!-- image goes here -->
      </div>
      <div class="product-info">
        <h1>{{ product }}</h1>
      </div>
    </div>
  </div>
</template>