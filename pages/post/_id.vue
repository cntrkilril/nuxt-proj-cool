<template>
  <div class="mt-2">
    <NuxtLink to="/post/" class="card-link">Вернуться к новостям</NuxtLink>
    <loading v-if="post.length === 0"/>
    <div class="d-flex flex-column" v-for="post in onePost" :key="post.id" >
      <h2 class="mt-2">{{ post.title }}</h2>
      <p class="">{{ post.body }}</p>
      <CommentsBlock :id="id"/>
    </div>
  </div>
</template>

<script>
import Loading from "../../components/loading";
import CommentsBlock from "../../components/commentsBlock";
export default {
  name: "index",
  components: {Loading, CommentsBlock},
  data() {
    return {
      id: '',
      post: []
    }
  },
  computed: {
    onePost() {
      this.id = this.$route.params.id
      this.post = this.$store.getters.allPosts.filter((element) => element.id + '1' === this.$route.params.id + '1')
      return this.post
    },
  },
}
</script>

<style scoped>

</style>
