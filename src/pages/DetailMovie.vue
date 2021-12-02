<template>
  <div>
      <Header/>
      <Sidebar/>
      <Detail :movie="movie" />
      <DetailRelated :movies="movies" />
      <Footer/>
  </div>
</template>

<script>
import axios from 'axios'

import Header from '../components/Header.vue'
import Sidebar from '../components/Sidebar.vue'
import Detail from '../components/Detail/Detail.vue'
import DetailRelated from '../components/Detail/DetailRelated.vue'
import Footer from '../components/Footer.vue'

export default {
    components: {
        Header,
        Detail,
        DetailRelated,
        Sidebar,
        Footer
    },
    data() {
        return {
            loading: true,
            movies:[],
            movie:{
                Title:'',
                Poster:'',
                Released:'',
                Language:'',
                Genre:'',
                Actors:'',
                Director:'',
                Runtime:''
            },
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
    methods: {
        detailMovie(id, apikey) {
            axios.get("https://www.omdbapi.com/?i="+id+"&apikey="+apikey)
            .then(res => {
                this.movie = res.data !== undefined ? res.data:this.movie 
                console.log('data', this.movie)
            })
            .catch((error) => console.log(error));
        },
    },
    watch: {
        '$route.params': {
            handler() {
                console.log('watch', this.$route.params.i)

                const id  = this.$route.params.i
                const apikey = this.$route.params.apikey
                
                this.detailMovie(id, apikey)
            },
            immediate: true,
        }
    },
}

</script>