<template>
  <v-card>
    <v-img :src="movie.img"/>
    <v-card-title>
      <h2>{{movie.title}}</h2>
      <v-rating medium v-model="editRating"></v-rating>
      <p>{{`${movie.rating}/5`}}</p>
    </v-card-title>
  </v-card>
</template>

<style>
</style>

<script>
export default {
  props: {
    movie: Object
  },
  data: () => ({
    editRating: 0
  }),
  created() {
    this.editRating = this.$props.movie.rating;
  },
 watch: {
    editRating: function() {
      this.$emit("change-rating", this.editRating);
    }
  }
};
</script>
