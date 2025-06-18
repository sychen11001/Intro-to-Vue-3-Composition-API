<script setup>
import { ref } from 'vue'

const details = ref(['50% cotton', '30% wool', '20% polyester'])

</script>
<template>
    <ul>
        <li v-for="detail in details">{{ detail }}</li>
    </ul>
</template>