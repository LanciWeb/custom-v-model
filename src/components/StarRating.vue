<template>
  <label>Rating:</label>
  <div class="d-flex">
    <FontAwesomeIcon
      v-for="n in maxRating"
      :key="n"
      :icon="getIcon(n)"
      role="button"
      @click="$emit('update:rating', n)"
    />
  </div>
</template>

<script>
export default {
  name: "StarRating",
  props: {
    maxRating: {
      type: Number,
      required: false,
      default: 5,
      validate(value) {
        if (!value.isInteger()) return false;
        return value > 0;
      },
    },
    rating: {
      type: Number,
      required: true,
      validate(value) {
        if (!value.isInteger()) return false;
        return value > 0 && value <= this.maxRating;
      },
    },
  },
  methods: {
    getIcon(n) {
      const iconType = this.rating >= n ? "fa-solid" : "fa-regular";
      return iconType + " fa-star";
    },
  },
};
</script>

<style>
.fa-star {
  color: goldenrod;
}
</style>