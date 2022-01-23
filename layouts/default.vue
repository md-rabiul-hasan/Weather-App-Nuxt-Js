<template>
  <v-app light>
    <v-main>
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