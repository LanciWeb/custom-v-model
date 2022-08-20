<template>
  <div class="container">
    <div class="card mt-5">
      <div class="card-header">
        <h2>Insert Movie</h2>
      </div>
      <div class="card-body">
        <form>
          <div class="mb-3">
            <label for="title" class="form-label">Title</label>
            <input
              id="title"
              type="text"
              v-model="title"
              class="form-control"
              placeholder="Insert the movie title"
            />
          </div>
          <div class="mb-3">
            <label for="plot" class="form-label">Plot</label>
            <textarea
              rows="5"
              id="plot"
              v-model="plot"
              class="form-control"
              placeholder="Insert the movie plot"
            ></textarea>
          </div>
          <div class="mb-3">
            <StarRating v-model:rating="rating" />
          </div>
        </form>
      </div>
    </div>
  </div>
  <hr />
  <section>
    <ul>
      <li><strong>Title</strong> {{ title }}</li>
      <li><strong>Plot</strong> {{ plot }}</li>
      <li><strong>Rating</strong> {{ rating }}</li>
    </ul>
  </section>
</template>

<script>
import StarRating from "./components/StarRating.vue";
export default {
  name: "App",
  data: () => ({ plot: "", title: "", rating: 3 }),
  components: { StarRating },
};
</script>

<style>
@import "~bootstrap/dist/css/bootstrap.min.css";
</style>
