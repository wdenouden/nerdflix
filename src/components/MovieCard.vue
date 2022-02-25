<template>
    <div class="card">
        <img :src="movie.urlPoster" />
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
    }

    .card img {
        box-shadow: rgba(0, 0, 0, 0.3) 0 5px 10px;
        min-height: 268px;
    }

    .card p {
        font-size: 12px;
        overflow-wrap: break-word;
    }

    .card span {
        opacity: 0.5;
        font-size: 12px;
    }
</style>