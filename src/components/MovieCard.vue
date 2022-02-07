<template>
    <div class="picture-card">
        <img class="poster"
        :src="`https://image.tmdb.org/t/p/original${movie.poster_path}`"
        alt="Poster not available" />
        <div class="description">
            <p>Titolo: <span>{{movie.title}}</span></p>
            <p>Titolo originale: <span>{{movie.original_title}}</span></p>
            <p>Lingua: 
                <img 
                :src="`/flags/${movie.original_language}.png`" 
                :alt="`${movie.original_language}`"/>
            </p>
            <p>Voto: 
                <span class="star"
                v-for="(star, index) in Math.round(movie.vote_average / 2)"
                :key="index"
                >
                &#9733;
                </span>
            </p>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        movie: Object
    }
}
</script>

<style lang="scss" scoped>
@import "@/style/cardstyle.scss";
</style>