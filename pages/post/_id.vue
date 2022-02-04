<template>
  <div class="mt-2">
    <NuxtLink to="/post" class="card-link">Вернуться к новостям</NuxtLink>
<!--    <div class="d-flex flex-column" v-for="post in onePost" :key="_id.id" >-->
<!--      <h2 class="mt-2">{{ _id.name }}</h2>-->
<!--      <p class="">{{ _id.desc }}</p>-->
<!--      <p class="align-self-end font-italic">{{ _id.date }}</p>-->
<!--      <CommentsBlock :comments="comments" @Submit="onSubmit"/>-->
<!--    </div>-->
  </div>
</template>

<script>
import CommentsBlock from "../../components/commentsBlock";

export default {
  name: "index",
  components: {CommentsBlock},
}
</script>

<style scoped>

</style>
