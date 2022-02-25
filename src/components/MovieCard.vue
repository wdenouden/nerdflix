<template>
    <div class="card">
        <div class="card_img">
            <img :src="movie.urlPoster" />
        </div>
        <div class="card_rating">
            <span>{{ movie.rating }}</span>
        </div>
        <p>{{ movie.title }}</p>
        <span>{{ movie.year }}</span>
    </div>
</template>

<script>
export default {
    name: 'MovieCard',
    props: {
        movie: JSON
    }
}
</script>

<style scoped>
    .card {
        margin-right: 30px;
        width: 182px;
        margin-bottom: 50px;
        position: relative;
    }

    .card img {
        box-shadow: rgba(0, 0, 0, 0.3) 0 5px 10px;
        min-height: 268px;
    }

    .card_img {
        position: relative;
        display: block;
    }

    .card_rating {
        position: absolute;
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
        width: 182px;
        height: 268px;
        text-align: center;
        background-color: rgba(0,0,0,0.8);
        opacity: 0;
        vertical-align: middle;
        line-height: 268px;
    }

    .card_rating:hover {
        opacity: 1;
    }

    .card_rating span {
        display: inline-table;
        vertical-align: middle;
        line-height: 100%;
        font-size: 52px !important;
    }

    .card p {
        margin-bottom: 0;
        font-size: 12px;
        overflow-wrap: break-word;
    }

    .card span {
        opacity: 0.5;
        font-size: 12px;
    }

</style>