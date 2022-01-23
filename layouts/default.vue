<template>
  <v-app light>
    <v-main>
      <v-toolbar color="indigo">
        <v-app-bar-nav-icon></v-app-bar-nav-icon>
        <v-toolbar-title>Title</v-toolbar-title>
        <v-spacer></v-spacer>

        <v-btn text>
          <nuxt-link to="/">Weather Application</nuxt-link>
        </v-btn>
      </v-toolbar>
      <transition>
        <v-content>
          <nuxt />
        </v-content>
      </transition>
    </v-main>
  </v-app>
</template>


<script>
export default {
  name: 'DefaultLayout',
}
</script>

<style scoped>
.v-application {
  background-color: #FFF;
  color:#000000
}
</style>