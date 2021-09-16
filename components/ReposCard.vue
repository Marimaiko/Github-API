<template>
  <v-card>
    <h3>{{repos.name}}</h3>
  </v-card>
</template>

<script lang="ts">
export default {
    props: {
    repos: {
      type: Object,
      default: () => {}
    }
  },
}
</script>
