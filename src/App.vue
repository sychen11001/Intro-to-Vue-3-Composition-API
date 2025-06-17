<script setup>
import { ref } from 'vue'

const product = ref('Boots')
const description = ref('description')

</script>

<template>
  <div class="product-display">
    <div class="product-container">
      <div class="product-info">
        <h1>{{ product }}</h1>
        <p>{{ 'description: ' + description }}</p>
      </div>
    </div>
  </div>
</template>