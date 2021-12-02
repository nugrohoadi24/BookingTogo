<template>
  <div>
      <Header/>
      <Sidebar/>
      <MovieList :movies="movies"/>
      <Footer/>
  </div>
</template>

<script>
import axios from 'axios'

import Header from '../components/Header.vue'
import Sidebar from '../components/Sidebar.vue'
import MovieList from '../components/AllMovies/MovieList.vue'
import Footer from '../components/Footer.vue'

export default {
    components: {
        Header,
        Sidebar,
        MovieList,
        Footer
    },
    data() {
        return {
            movies:[],
            key:'271ab1b1',
            default:'Batman',
        }
    },
    mounted() {
        axios
        .get('https://www.omdbapi.com/?s='+this.default+'&page=1&apikey='+this.key)
        .then(res => (
            this.movies = res.data.Search !== undefined && res.data.Response == "True" ? res.data.Search:[]
        ))
        .catch(err => console.log(err));

        
    },
}

</script>