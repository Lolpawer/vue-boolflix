<template>
    <div class="picture-card">
        <p>Titolo: <span>{{movie.title}}</span></p>
        <p>Titolo originale: <span>{{movie.original_title}}</span></p>
        <p>Lingua: 
            <img 
            :src="`/flags/${movie.original_language}.png`" 
            :alt="` ${movie.original_language}`"/>
        </p>
        <p>Voto: <span>{{movie.vote_average}}</span></p>
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
    .picture-card {
        margin: 0 10px;
        min-width: 300px;
        height: 400px;
        background-color: #fff;
        border: 2px solid #000;
        overflow-y: auto;

        p {
            font-weight: bold;
            padding: 10px 10px;
            font-size: 13px;
            color: #c60000;

            span {
                color: #000;
            }

            img {
                width: 25px;
                height: 19px;
            }
        }
    }

</style>