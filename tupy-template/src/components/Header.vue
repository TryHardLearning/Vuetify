<template>
    <v-toolbar color="#305b97">
      <v-btn icon="mdi-chevron-left" @click.stop="toggleRail"></v-btn>
      <v-toolbar-title>Tipo Cadastro</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn icon>
        <v-badge color="error" content="2">
          <v-icon>mdi-bell-outline</v-icon>
        </v-badge>
      </v-btn>
      <v-btn icon>
        <v-icon>mdi-cog-outline</v-icon>
      </v-btn>
    </v-toolbar>
  </template>
  
  <script lang="ts">
  import { Vue, Options } from 'vue-class-component';
  
  @Options({
    props: {
      rail: Boolean
    }
  })
  export default class Header extends Vue {
    toggleRail() {
      this.$emit('toggle-rail');
    }
  }
  </script>
  
  <style scoped></style>
  