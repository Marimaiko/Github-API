<template>
  <v-container class="mx-auto">
    <v-card class="d-flex">
      <v-col>
        <div class="ma-10">
          <h1>Usuários do Github</h1>
          <v-form class="mt-10">
            <v-text-field
              label=""
              required
            >
            <input type="text" v-model="username">
            </v-text-field>
          </v-form>
          <div class="d-inline-flex pa-2 flex-wrap">
            <UserCard
              v-for="data in users"
              :key="data.id"
              :user='data'
            />
          </div>
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

<script lang='ts'>
import axios from 'axios';

export default {
  data() {
    return {
      users:[],
      username:''
    }
  },

  created: function () {
    axios
      .get(`https://api.github.com/users`)
      .then((res) => {
        this.users = res.data;
      })
      .catch((err) => console.log(err));
  },

}
</script>
