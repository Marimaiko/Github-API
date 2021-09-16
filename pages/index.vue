<template>
  <v-app>
    <v-main>
      <v-container >
        <v-card class="pa-10">
          <h1>Faça sua consulta</h1>
          <div class="py-10">
            <v-btn
              elevation="2"
              raised
              link to="/user"
            >Usuário</v-btn>
            <v-btn
              elevation="2"
              raised
              link to="/repository"
            >Repositório</v-btn>
          </div>
        </v-card>
      </v-container>
    </v-main>
  </v-app>
</template>
