<template>
    <div>
        <section class="movie-list">
            <div class="container">
                <div class="row justify-content-center">
                    <div class="col-md-3 blank-show"></div>
                    <div class="col-md-9">
                        <h3 class="text-heading text-center text-white">Now Playing Movie</h3>
                    </div>
                </div>
                <div class="row justify-content-center">
                    <div class="col-md-3 blank-show">
                    </div>
                    <div class="col-md-9">
                        <div class="row my-3">
                            <div class="col-lg-3 col-md-6 my-1" v-for="movie in movies" v-bind:key="movie.imdbID">
                                <router-link :to="'/detail/'+movie.imdbID+'/271ab1b1'">
                                    <div class="card card-image card-shadow my-2">
                                        <img v-bind:src="movie.Poster" :alt="movie.Title" >
                                        <div class="text-description text-center text-white mt-2">{{ movie.Title }}</div>
                                    </div>
                                </router-link>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </div>
</template>

<script>

export default {
    data() {
        return {
            
        }
    },
    props: {
        movies:Array
    },
    mounted() {

    }
}
</script>

<style>

</style>