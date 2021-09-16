<template>
  <v-card
    class="mx-auto pa-2"
    width="300"
  >
  <v-img
    :src="user.avatar_url"
    height="200px"
  ></v-img>

  <v-card-title>
    {{user.login}}
  </v-card-title>

  <v-card-subtitle>
    <a :href="user.html_url">{{user.html_url}}</a>
  </v-card-subtitle>

  <v-card-actions>
    <v-btn
      color="orange lighten-2"
      text
      @click="show = !show"
    >
      Repositórios
      <v-icon
      >{{ show ? 'mdi-chevron-up' : 'mdi-chevron-down' }}</v-icon>
    </v-btn>

  <v-spacer></v-spacer>
  </v-card-actions>
    <v-expand-transition>
      <div v-show="show">
        <v-divider></v-divider>
        <v-card-text >
          <a :href="user.repos_url">{{user.repos_url}}</a>
        </v-card-text>
      </div>
    </v-expand-transition>
  </v-card>
</template>

<script lang="ts">
import axios from 'axios';

  export default{
    data: () => ({
        show: false,
        currentUrl:'',
        repos:''
      }),
    props: {
      user: {
        type: Object,
        default: () => {}
      }
    },
    // methods: {
    //   setUserUrl(url) {
    //     this.currentUrl = url
    //   }
    // },

  //   created: function () {
  //   axios
  //     .get(this.currentUrl)
  //     .then((res) => {
  //       this.repos = res.data.name;
  //     })
  //     .catch((err) => console.log(err));
  // }
  }
</script>
