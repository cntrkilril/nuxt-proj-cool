<!--<template>-->
<!--  <div class="">-->
<!--    <h3 class="">Комментарии</h3>-->
<!--    <b-form @submit="Submit" @reset="Reset" v-if="show">-->
<!--      <b-form-group-->
<!--        id="input-group-1"-->
<!--        label="Имя комментатора"-->
<!--        label-for="input-1"-->
<!--        description="Данное имя будет демонстироваться в комментарии"-->
<!--      >-->
<!--        <b-form-input-->
<!--          id="input-1"-->
<!--          v-model="form.name"-->
<!--          placeholder="Введите имя"-->
<!--          required-->
<!--        ></b-form-input>-->
<!--      </b-form-group>-->
<!--      <b-form-group-->
<!--        id="input-group-2"-->
<!--        label="Текст комментария"-->
<!--        label-for="input-2"-->
<!--      >-->
<!--        <b-form-input-->
<!--          id="input-2"-->
<!--          v-model="form.text"-->
<!--          placeholder="Введите"-->
<!--          required-->
<!--        ></b-form-input>-->
<!--      </b-form-group>-->
<!--      <b-button type="submit" variant="primary">Отправить</b-button>-->
<!--      <b-button type="reset" variant="danger">Очистить</b-button>-->
<!--    </b-form>-->
<!--    <div class="mt-2">-->
<!--      <div class="" v-if="comments.length === 0">Комментарии прогружаются или их нет</div>-->
<!--      <b-card class="mb-2" v-for="comment in comments" :key="comment.id" bg-variant="dark" text-variant="white" :title="comment.user_name">-->
<!--        <b-card-text>-->
<!--          {{ comment.comment }}-->
<!--        </b-card-text>-->
<!--      </b-card>-->
<!--      </div>-->
<!--  </div>-->
<!--</template>-->

<!--<script>-->
<!--export default {-->
<!--  name: "CommentsBlock",-->
<!--  props: {-->
<!--    comments: null,-->
<!--    load: false-->
<!--  },-->
<!--  data() {-->
<!--    return {-->
<!--      show: true,-->
<!--      form: {-->
<!--        name: '',-->
<!--        text: '',-->
<!--      }-->
<!--    }-->
<!--  },-->
<!--  methods: {-->
<!--    Submit(event) {-->
<!--      event.preventDefault()-->
<!--      var params = {-->
<!--        user_name: this.form.name,-->
<!--        comment: this.form.text,-->
<!--        id: this.$route.params.id,-->
<!--      }-->
<!--      console.log(this.comments.length)-->
<!--      this.$emit('Submit',params)-->
<!--      this.form.name = ''-->
<!--      this.form.text = ''-->
<!--    },-->
<!--    Reset(event) {-->
<!--      event.preventDefault()-->
<!--      }-->
<!--    }-->
<!--  }-->
<!--</script>-->

<!--<style scoped>-->

<!--</style>-->
