<template>
  <div class="">
    <h3 class="">Комментарии</h3>
    <loading v-if="comments.length === 0"/>

    <div class="mt-2">
      <div class="" v-if="comments.length === 0">Комментарии прогружаются или их нет</div>
      <b-card class="mb-2" v-for="comment in comments" :key="comment.id" bg-variant="dark" text-variant="white" :title="comment.email">
        <b-card-text>
          {{ comment.body }}
        </b-card-text>
      </b-card>
    </div>
    <b-form @submit="Submit" @reset="Reset" v-if="show">
      <b-form-group
        id="input-group-1"
        label="Имя комментатора"
        label-for="input-1"
        description="Данное имя будет демонстироваться в комментарии"
      >
        <b-form-input
          id="input-1"
          v-model="form.name"
          placeholder="Введите имя"
          required
        ></b-form-input>
      </b-form-group>
      <b-form-group
        id="input-group-2"
        label="Текст комментария"
        label-for="input-2"
      >
        <b-form-input
          id="input-2"
          v-model="form.text"
          placeholder="Введите"
          required
        ></b-form-input>
      </b-form-group>
      <b-button type="submit" variant="primary">Отправить</b-button>
      <b-button type="reset" variant="danger">Очистить</b-button>
    </b-form>
  </div>
</template>

<script>
import Loading from "./loading";
export default {
  name: "CommentsBlock",
  components: {Loading},
  props: {
    id: {
      type: String,
      default: ''
    },
  },
  data() {
    return {
      comments: {
        type: Array,
        default: []
      },
      show: true,
      form: {
        name: '',
        text: ''
      }
    }
  },
  beforeMount() {
    this.getComments()
  },
  methods: {
    async getComments() {
      await fetch(`https://jsonplaceholder.typicode.com/posts/${this.id}/comments`, {
        method: 'GET',
      }).then((res) => {
        return res.json()
      }).then((result) =>
      this.comments = result)
      console.log(this.comments)
    },

    Submit(event) {
      event.preventDefault()
      this.comments.push({
        email: this.form.name,
        body: this.form.text,
      })
      const res = fetch(`https://jsonplaceholder.typicode.com/posts/${this.id}/comments`, {
          method: 'POST',
          body: JSON.stringify({
            email: this.form.name,
            body: this.form.text,
          })
        })
      console.log(res)
      this.form.name = ''
      this.form.text = ''
    },

    Reset(event) {
      event.preventDefault()
      this.form.name = ''
      this.form.text = ''
      }
    }
}
</script>

<style scoped>

</style>
