<template>
  <v-app id="app">
    <v-container fluid>
      <v-layout align-center justify-center>
        <v-flex xs12 class="text-xs-center">
          <img src="./assets/logo.png">
        </v-flex>
      </v-layout>
      <v-layout align-center justify-center>
        <router-view></router-view>
      </v-layout>
    </v-container>
  </v-app>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
