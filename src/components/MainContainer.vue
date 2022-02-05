<template>
    <main>
        <div>
            <div class="picture-container d-flex p-3">
                <movie-card
                v-for="movie in movies"
                :key="movie.id"
                :movie="movie"/>
            </div>
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

        .picture-container {
            overflow-x: auto;
        }
    }
</style>