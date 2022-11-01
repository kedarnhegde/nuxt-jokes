<template>
  <div class="container">
    <nuxt-link to="/"> Back </nuxt-link>
    <br />
    <h1>List of Jokes</h1>
    <Joke v-for="joke in jokes" :key="joke.id" :id="joke.id" :joke="joke.joke" />
  </div>
</template>

<script>
  import axios from "axios";
  import Joke from '../../components/Joke.vue';

  export default {
    components: {
      Joke
    },
    data() {
      return {
        jokes: []
      }
    },
    head() {
        return {
            title: 'List of Jokes'
        }
    },
    async created() {
      const config = {
        headers: {
          'Accept': 'application/json'
        }
      }
      try {
        const res = await axios.get('https://icanhazdadjoke.com/search', config);
        this.jokes = res.data.results;
        
      } catch (err) {
        console.log(err);
      }
      
    }
  }
</script>

<style>

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 1rem;
  line-height: 1.6;
  background: #f4f4f4;
}

a {
  color: #666;
  text-decoration: none;
}

ul {
  list-style: none;
}

.container {
  max-width: 800px;
  margin: 2rem auto;
  overflow: hidden;
  padding: 1rem 2rem;
  background: #fff;
}




</style>  