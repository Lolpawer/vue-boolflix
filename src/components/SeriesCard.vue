<template>
    <div class="picture-card">
        <p>Titolo: <span>{{show.name}}</span></p>
        <p>Titolo originale: <span>{{show.original_title}}</span></p>
        <p>Lingua: 
            <img 
            :src="`/flags/${show.original_language}.png`" 
            :alt="` ${show.original_language}`"/>
        </p>
        <p>Voto: <span>{{show.vote_average}}</span></p>
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