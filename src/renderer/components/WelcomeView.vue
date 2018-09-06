<template>
  <v-layout row wrap justify-center id="wrapper">
    <v-flex xs12 md4 offset-md1 class="text-xs-center centered">
      <img id="logo" class="logo" src="~@/assets/logo.png" alt="electron-vue">
    </v-flex>
    <v-flex xs10 class="mt-3">
      <v-card>
        <v-card-text>
          <p>Welcome to my météo app.</p>
          <p>Search for a city to display the weather</p>
          <v-text-field label="City" box v-model="city"></v-text-field>
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn primary flat router @click="getWeather">Search</v-btn>
        </v-card-actions>
      </v-card>
    </v-flex>
    <v-flex xs10 class="mt-3">
      <v-card>
        <v-card-text>
          <h1>{{temp}}°F</h1>
          <p>Min Temperature : {{ tempMin }}</p>
          <p>Max Temperature : {{ tempMax }}</p>
          <p>Humidity : {{ humidity }}</p>
        </v-card-text>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
  import SystemInformation from './WelcomeView/SystemInformation'
  import axios from 'axios'
  axios.defaults.baseURL = 'http://api.openweathermap.org/data/2.5'
  export default {
    name: 'welcome',
    components: { SystemInformation },
    data () {
      return {
        city: '',
        country: '',
        weatherDescription: '',
        temp: null,
        tempMin: null,
        tempMax: null,
        humidity: null,
        key: '863668499362fb4884ebd97229f3b26b',
        url: 'http://api.openweathermap.org/data/2.5/weather'
      }
    },
    methods: {
      open (link) {
        this.$electron.shell.openExternal(link)
      },
      getWeather () {
        axios.get(this.url, {
          params: {
            q: this.city,
            appid: this.key
          }
        }).then(response => {
          console.log(response.data)
          this.temp = response.data.main.temp
          this.tempMax = response.data.main.temp_max
          this.tempMin = response.data.main.temp_min
          this.humidity = response.data.main.humidity
        }).catch(errors => {
          console.log(errors)
        })
      }
    }
  }
</script>

<style scoped>
  .centered
  {
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .logo
  {
    max-width: 100%;
  }
</style>
