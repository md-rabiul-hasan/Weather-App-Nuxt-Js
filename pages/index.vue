<template>
  <v-container>
    <h1 class="text-center mb-4">Weather Application By Nuxt-Js</h1>
    <v-flex xs12>
        <v-card color="blue-gray darken-2">
          <v-card-text>Card Content</v-card-text>
        </v-card>
    </v-flex>
    <v-flex xs12 class="mt-4">
     <v-text-field  label="Enter City"  solo></v-text-field>
    </v-flex>
  </v-container>
</template>

<script>
export default {
  name: 'IndexPage',
}
</script>

<style>

</style>