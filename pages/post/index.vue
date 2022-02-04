<template>
  <div class="">
    <h2 class="mt-2 mb-2">Все посты</h2>
    <loading v-if="posts.length === 0"/>
      <b-card class="mb-2" v-for="post in allPosts" :key="post.id" bg-variant="dark" text-variant="white" :title="post.title">
        <b-card-text>
          {{ post.body }}
        </b-card-text>
        <NuxtLink :to="'/post/'+post.id+'/'" class="btn btn-primary">Читать полностью</NuxtLink>
      </b-card>
  </div>
</template>

<script>
import Loading from "../../components/loading";
export default {
  name: "index",
  components: {Loading},
  data() {
    return {
      posts: []
    }
  },
  computed: {
    allPosts() {
      this.posts = this.$store.getters.allPosts
      return this.posts
    }
  },
}
</script>

<style scoped>

</style>
