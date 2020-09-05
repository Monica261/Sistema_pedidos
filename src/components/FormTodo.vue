<template>
  <div class="form-todo form-group">
  <p>
    <input placeholder="nome" type="text" name="author" class="form-control" v-model="name" />
  </p>
  <p>
    <input placeholder="hamburguer" type="text" name="hamburguer" class="form-control" v-model="hamburguer" />
  </p>
  <p>
    <input placeholder="bebida" type="text" name="bebida" class="form-control" v-model="bebida" />
  </p>
  <p>
    <textarea placeholder="Comentário" name="message"  class="form-control" v-model="message"></textarea>
  </p>
  <button v-on:click="addComment" type="submit" class="btn btn-md btn-info">Comentar</button>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        name: '',
        hamburguer: '',
        bebida: '',
        message: ''
      }
    },
    methods: {
      addComment() {
        if (this.message.trim() === '') {
          return;
        }
        this.$emit('add-todo', {
          name: this.name,
          hamburguer: this.hamburguer,
          bebida: this.bebida,
          message: this.message,
        });
        this.name = '';
        this.hamburguer = '',
        this.bebida = '',
        this.message = '';
      }
    }
  }
</script>