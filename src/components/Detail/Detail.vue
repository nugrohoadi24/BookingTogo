<template>
    <div>
        <section class="movie-list">
            <div class="container">
                <div class="row justify-content-center">
                    <div class="col-md-3 blank-show"></div>
                    <div class="col-md-9">
                        <h3 class="text-title text-heading text-white">{{ movie.Title }}</h3>
                        <div class="row mt-4">
                            <div class="col-md-3">
                                <div class="card card-image card-shadow w-100">
                                    <img v-bind:src="movie.Poster" :alt="movie.Title" class="" >
                                </div>
                            </div>
                            <div class="col-md-9 text-white">
                                <p class="text-description">Relase Date : {{ movie.Released }}</p>
                                <p class="text-description">Language : {{ movie.Language }}</p>
                                <p class="text-description">Genre : {{ movie.Genre }}</p>
                                <p class="text-description">Cast & Crew : {{ movie.Actors }}</p>
                                <p class="text-description">Director : {{ movie.Director }}</p>
                                <p class="text-description">Length : {{ movie.Runtime }}</p>
                                <div>
                                    <h4 class="text-title my-3">Sinopsis</h4>
                                    <p class="text-description my-4">{{ movie.Plot }}</p>
                                </div>
                                <div>
                                    <button class="btn btn-action-detail mr-2">Buy Ticket</button>
                                    <button class="btn btn-action-detail">Watch Trailer</button>
                                </div>
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
    props: {
        movie:Object,
    },
}
</script>

<style>

</style>