<script setup>
import { reactive } from 'vue'

const review = reactive({
  name: '',
  content: '',
  rating: null,
  recommend: ''
})

const emit = defineEmits(['review-submitted'])

const OnSubmit = () => {
  if (review.name === '' || review.content === '' || review.rating === null || review.recommend === '') {
    alert('评论不完整，请填写所有字段。')
    return
  }
  const productReview = {
    name: review.name,
    content: review.content,
    rating: review.rating,
    recommend: review.recommend
  }
  emit('review-submitted', productReview)

  // 重置表单
  review.name = ''
  review.content = ''
  revieww.rating = null
  review.recommend = ''
}
</script>
<template>
  <form class="review-form" @submit.prevent="OnSubmit">
    <h3>Leave a review</h3>
    <label for="name">Name:</label>
    <input id="name" v-model="review.name">

    <label for="review">Review:</label>
    <textarea id="review" v-model="review.content"></textarea>

    <label for="rating">Rating:</label>
    <select id="rating" v-model.number="review.rating">
      <option>5</option>
      <option>4</option>
      <option>3</option>
      <option>2</option>
      <option>1</option>
    </select>

    <label for="recommend">Would you recommend this product?</label>
    <select id="recommend" v-model="review.recommend">
      <option value="yes">Yes</option>
      <option value="no">No</option>
    </select>
    <input class=" button" type="submit" value="Submit">
  </form>
</template>