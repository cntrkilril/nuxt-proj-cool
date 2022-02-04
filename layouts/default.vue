<template>
  <div class="">
    <Header/>
    <div class="container">
      <Nuxt/>
    </div>
  </div>
</template>

<script>
import Header from "../components/header";
export default {
  name: "default",
  components: {Header},
  async beforeMount() {
    this.$store.dispatch('fetchPosts')
  },
}
</script>
