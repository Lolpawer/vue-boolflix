<template>
    <div class="picture-card">
        <img class="poster"
        :src="`https://image.tmdb.org/t/p/original${show.poster_path}`"
        alt="Poster not available" />
        <div class="description">
            <p>Titolo: <span>{{show.name}}</span></p>
            <p>Titolo originale: <span>{{show.original_title}}</span></p>
            <p>Lingua: 
                <img 
                :src="`/flags/${show.original_language}.png`" 
                :alt="`${show.original_language}`"/>
            </p>
            <p>Voto:
                <span class="star"
                v-for="(star, index) in Math.round(show.vote_average / 2)"
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
        show: Object
    }
}
</script>

<style lang="scss" scoped>
@import "@/style/cardstyle.scss";
</style>