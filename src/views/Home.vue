<template>
  <div class="home">
    <div class="post" v-for="post in allPosts" :key="post.id">
      <h2>{{ post.title }}</h2>
      <p>{{ post.body }}</p>
    </div>
  </div>
</template>

<script>
import { mapGetters } from "vuex";

// @ is an alias to /src

export default {
  name: "Home",
  computed: mapGetters(["allPosts"]),

  async mounted() {
    this.$store.dispatch("fetchPosts");
  },
};
</script>
<style>
.home {
  margin: 60px auto;
}
.post {
  margin: 20px;
  width: 300px;
  border: 1px solid #ccc;
  border-radius: 5px;
  margin-bottom: 1rem;
}
</style>
