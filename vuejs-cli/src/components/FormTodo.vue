<template>
  <div class="form-todo form-group">
    <p>
      <input type="text" placeholder="Nome" name="autor" class="form-control" v-model="name" />
    </p>
    <p>
      <textarea placeholder="Comentário" name="message" class="form-control" v-model="message"></textarea>
    </p>
    <button type="submit" v-on:click="addComment" class="btn btn-primary">Comentar</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      message: ""
    };
  },
  methods: {
    addComment() {
      if (this.message.trim() === "") return;

      this.$emit('add-todo', {
        name: this.name,
        message: this.message,
      });

      this.name = "";
      this.message = "";
    }
  }
};
</script>

