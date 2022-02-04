<template>
  <div class="">
    <h2 class="mt-2 mb-2">Все посты</h2>
      <b-card class="mb-2" v-for="post in allPosts" :key="post.id" bg-variant="dark" text-variant="white" :title="post.name">
        <b-card-text>
          {{ post.shortDesc }}
        </b-card-text>
        <NuxtLink :to="'/post/'+post.id+'/'" class="btn btn-primary">Читать полностью</NuxtLink>
      </b-card>
  </div>
</template>

<script>
export default {
  name: "index",
  computed: {
    allPosts() {
      return this.$store.getters.allPosts;
    }
  },
}
</script>

<style scoped>

</style>
