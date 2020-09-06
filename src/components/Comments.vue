<template>
  <div class="container">
    <h1>Pedidos</h1>
    <hr />
    <FormTodo v-on:add-todo="addComment"></FormTodo>
    <div class="list-group">
    <p v-if="comments.length <= 0">Sem Pedidos...</p>
    <div v-else class="list-group-item" v-for="(comment, index) in allComments" v-bind:key="index">
        <span class="comment__author"><strong>Autor: </strong>{{ comment.name }}</span>
        <p><strong>Hamburguer: </strong>{{ comment.hamburguer }}</p>
        <p><strong>Bebida: </strong>{{ comment.bebida }}</p>
        <p><strong>Comentário: </strong>{{ comment.message }}</p>
        <div>
        <a href="#" title="Excluir" v-on:click.prevent="removeComment(index)"><button class="btn btn-md btn-danger">Excluir</button></a>
        </div>
    </div>
    </div>
    <hr />
  </div>
</template>

<script>
import FormTodo from './FormTodo';
export default {
  components: {
    FormTodo
  },
  data() {
    return {
      comments: []
    }
  },
  methods: {
    addComment(comment) {
      this.comments.push(comment);
    },
    removeComment(index) {
      this.comments.splice(index, 1);
    }
  },
  computed: {
    allComments() {
      return this.comments.map(comment => ({
        ...comment,
        name: comment.name.trim() === '' ? 'Anônimo' : comment.name
      }))
    }
  },
  watch: {
    comments(val) {
      console.log('val', val)
    }
  }
}
</script>