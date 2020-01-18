<template>
  <b-form inline class="justify-content-center" @submit.prevent="addPerson">
    <label class="sr-only" for="inline-form-input-name">Name</label>
    <b-input
      v-model="name"
      id="inline-form-input-name"
      class="mb-2 mr-sm-2 mb-sm-0"
      placeholder="Jane Doe"
    ></b-input>

    <label class="sr-only" for="inline-form-input-username">E-mail</label>
    <b-input-group prepend="@" class="mb-2 mr-sm-2 mb-sm-0">
      <b-input id="inline-form-input-username" v-model="email" placeholder="john@doe.com"></b-input>
    </b-input-group>
    <b-button type="submit" variant="primary">Salvar</b-button>
  </b-form>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      email: ""
    };
  },
  methods: {
    addPerson() {
      const person = { nome: this.name, email: this.email };
      this.$emit("onAddPerson", person);
    }
  }
};
</script>