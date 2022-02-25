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
    .card img {
        box-shadow: rgba(0, 0, 0, 0.3) 0 5px 10px;
    }

    .card p {
        font-size: 12px;
    }

    .card span {
        opacity: 0.5;
        font-size: 12px;
    }
</style>