<template>
  <div class="container">
    <SearchJoke @onSearch="searchJokes"/>
    <Joke v-for="joke in jokes" :key="joke.id" :joke="joke.joke" :id="joke.id" />
  </div>
</template>

<script>
import axios from 'axios'
import Joke from '@/components/Joke'
import SearchJoke from '@/components/SearchJoke'

export default {
  components: {
    Joke,
    SearchJoke
  },
  head() {
    return {
      title: 'DadJokes'
    }
  },
  data () {
    return {
      jokes: []
    }
  },
  created() {
    this.searchJokes()
  },
  methods: {
    async searchJokes(text = '') {
      const config = {
        headers: {
          'Accept': 'application/json'
        }
      }
      try{
        const { data: { results } } = await axios.get('https://icanhazdadjoke.com/search?term='+text, config)
        this.jokes = results
      } catch(e) {
        console.log(e)
      }
    }
  }
}
</script>

<style

</style>