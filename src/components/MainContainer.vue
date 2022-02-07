<template>
    <main>
        <div>
            <h1>Film</h1>
            <div class="picture-container d-flex p-3">
                <movie-card
                v-for="movie in movies"
                :key="movie.id"
                :movie="movie"/>
            </div>
            <h1>Serie TV</h1>
            <div class="picture-container d-flex p-3">
                <series-card
                v-for="show in series"
                :key="show.id"
                :show="show"/>
            </div>
        </div>
    </main>
</template>

<script>
import MovieCard from './MovieCard.vue'
import SeriesCard from './SeriesCard.vue'

export default {
    components: {
        MovieCard,
        SeriesCard
    },
    props: {
        movies: Array,
        series: Array
    }
}
</script>

<style lang="scss" scoped>
    main {
        min-height: calc(100vh - 56px);
        background-color: #434343;

        h1 {
            color: #fff;
            padding-left: 15px;
            padding-top: 5px;
        }

        .picture-container {
            overflow-x: auto;
        }
    }
</style>