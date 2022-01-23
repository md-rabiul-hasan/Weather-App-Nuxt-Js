<template>
  <v-container>
    <h1 class="text-center mb-4">Weather Application By Nuxt-Js</h1>
     <v-flex xs12>
       <v-form @submit.prevent="getWeatherInfo">
          <v-text-field  label="Enter City" v-model="city"  solo></v-text-field>
       </v-form>      
    </v-flex>
    <v-flex xs12>
        <v-card color="blue-gray darken-2" v-if="weather.weather">
          <v-card-text>
            <v-layout justify-center>
              <v-flex class="text-center" width="40%">
                <h4>Temperature</h4>
                <h1>{{ weather.name }}</h1>
                <img :src="icon" alt="weather-icon" />
                <p>
                  <span class="display-1">{{ temp() }} &deg;C</span> 
                  <span class="caption ml-4">{{ weather.weather[0].description }}</span>
                </p>
              </v-flex>
              <v-flex xs4 class="text-center">
              <h4>Wind</h4>
              <p>
                <span>  {{ weather.wind.speed }} m/s ({{ weather.wind.deg }}  &deg;) </span>
              </p>
              <h4>Humidity</h4>
              <p>
                <span>  {{ weather.main.humidity }} % </span>
              </p>

               <h4>Pressure</h4>
              <p>
                <span>  {{ weather.main.pressure }} hPa </span>
              </p>
               
            </v-flex>
            <v-flex xs4 class="text-center">
               <h4>Max Temperature</h4>
              <p>
                <span>   {{ Math.round(weather.main.temp_max - 273) }} &deg; C </span>
              </p>
               <h4>Min Temperature</h4>
              <p>
                <span>  {{ Math.round(weather.main.temp_min - 273) }} &deg; C </span>
              </p>              
            </v-flex>
            </v-layout>
          </v-card-text>
        </v-card>
    </v-flex>
   
  </v-container>
</template>

<script>
export default {
  name: 'IndexPage',
  data(){
    return {
      city: "",
      weather: {}
    }
  },
  computed:{
    icon(){
      return this.weather.weather ? `https://openweathermap.org/img/w/${this.weather.weather[0].icon}.png` : ''
    }
  },
  methods:{
    getWeatherInfo(){
      this.$axios
    .$get(
      `https://api.openweathermap.org/data/2.5/weather?q=${this.city}&appid=dd7bffa3ce52db5819ffaffdd02d83f6`
    )
    .then(response => (this.weather  = response))
    },
     temp() {
      return Math.round(this.weather.main.temp - 273)
    }
  }
}
</script>

<style>

</style>