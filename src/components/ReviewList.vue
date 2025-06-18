<script setup>

const props = defineProps({
    reviews: {
        type: Array,
        required: true
    }
})

</script>
<template>
    <div class="review-container">
        <h3>Review:</h3>
        <ul v-for="(review, index) in reviews" :key="index">
            <span>{{ review.name }} gave this {{ review.rating }} stars</span>
            <br />
            <span>"{{ review.content }}"</span>
            <br />
            <span>recommend: {{ review.recommend }}</span>
        </ul>
    </div>
</template>