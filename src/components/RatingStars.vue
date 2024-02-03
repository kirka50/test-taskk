<template>
  <div class="rating-stars">
    <div v-for="i in 5" :key="i">
      <div v-if="(i <= rating)" >
        <img src="@/assets/starIcon.svg" height="20" width="19"/>
      </div>
      <div v-else-if="i - rating == 0.5">
        <img src="@/assets/halfStarIcon.svg" height="20" width="19"/>
      </div>
      <div v-else>
        <img src="@/assets/grayStarIcon.svg" height="20" width="19"/>
      </div>
    </div>
  </div>

</template>

<script>
export default {
  name: "RatingStars",
  props: {
    rating: {
      type: Number,
      default: 5
    }
  }
}
</script>

<style scoped>
  .rating-stars {

    display: flex;
    flex-direction: row;
    gap: 4px;
  }
</style>