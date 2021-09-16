<template>
  <v-container  class="mx-auto">
    <v-card class="d-flex">
      <v-col>
        <div class="ma-10">
          <h1>Pesquise os repositórios de alguém do Github</h1>
          <v-form class="mt-10">
            <v-text-field
              v-model="user"
              label="Insira o nome de um USUÁRIO"
              required
            >
            </v-text-field>
          </v-form>
          <ReposCard
            v-for='repos in repos'
            :key="repos.id"
            :repos= "repos"
          />
        </div>
        <v-btn
          elevation="2"
          raised
          link to="/"
        >Voltar</v-btn>
      </v-col>
    </v-card>
  </v-container>
</template>

<script lang="ts">
import axios from 'axios';

export default{
  data() {
    return {
      user:'',
      repos:[]
    }
  },

  created: function () {
    axios
      .get(`https://api.github.com/users/${this.user}/repos`)
      .then((res) => {
        this.repos = res.data;
      })
      .catch((err) => console.log(err));
  },
}
</script>
