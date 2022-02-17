<template>
  <div class="container">
    <nuxt-link to="/jokes" style="text-decoration:underline;">Back To Jokes</nuxt-link>
    <h3 style="margin-top:15px;">{{ joke }}</h3>
    <hr>
    <small> Joke ID: {{ $route.params.id }}</small>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      joke: 'loading...'
    }
  },
  created() {
    this.getJoke()
  },
  methods: {
    async getJoke() {
      const config = {
        headers: {
          'Accept': 'application/json'
        }
      }
      try{
        const { data: { joke } } = await axios.get('https://icanhazdadjoke.com/j/' + this.$route.params.id, config)
        this.joke = joke
      } catch(e) {
        console.log(e)
      }
    }
  }
}
</script>

<style>

</style>