<template>
  <div>
    <h2>Registro de Usuario</h2>
    <hr />
    <div class="columns is-centered">
      <div class="column is-half">
        <p>Nome</p>
        <input
          class="input"
          type="text"
          placeholder="Nome do usuario"
          v-model="name"
        />
        <p>E-mail</p>
        <input
          class="input"
          type="email"
          placeholder="email@email.com"
          v-model="email"
        />
        <p>Senha</p>
        <input
          class="input"
          type="password"
          placeholder="******"
          v-model="password"
        />
        <hr />
        <button class="button is-success" @click="register">Cadastrar</button>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      name: "",
      password: "",
      email: "",
    };
  },
  methods: {
    async register() {
      await axios
        .get("https://622a05e5be12fc4538afb46c.mockapi.io/todo", (res) => {
          console.log(res);
        })
        .catch((err) => {
          console.log(err);
        });
    },
  },
};
</script>

<style></style>
