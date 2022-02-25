<template>
    <div class="card">
        <div class="card_img">
            <img :src="movie.urlPoster" />
        </div>
        <div class="card_rating">
            <span>{{ movie.rating }}</span>
        </div>
        <div class="card_like" @click="updateFavorite">
            <svg v-if="!favorite" width="20" height="19" viewBox="0 0 20 19" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path opacity="0.503" fill-rule="evenodd" clip-rule="evenodd" d="M9.99999 15L5.01887 17.6187C4.65206 17.8116 4.22334 17.5001 4.2934 17.0916L5.24471 11.5451L1.2149 7.617C0.91814 7.32773 1.08189 6.82374 1.492 6.76415L7.06106 5.95492L9.55162 0.908498C9.73503 0.536875 10.2649 0.536875 10.4484 0.908498L12.9389 5.95492L18.508 6.76415C18.9181 6.82374 19.0818 7.32773 18.7851 7.617L14.7553 11.5451L15.7066 17.0916C15.7766 17.5001 15.3479 17.8116 14.9811 17.6187L9.99999 15Z" stroke="white"/>
            </svg>

            <svg v-if="favorite" width="18" height="19" viewBox="0 0 18 19" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path fill-rule="evenodd" clip-rule="evenodd" d="M8.99997 15.3311L3.97602 17.9464C3.60892 18.1375 3.18185 17.8253 3.25248 17.4175L4.21069 11.8856L0.15621 7.97222C-0.143023 7.6834 0.0205978 7.17679 0.432239 7.11756L6.04003 6.31069L8.55247 1.26989C8.73653 0.900607 9.26341 0.900607 9.44746 1.26989L11.9599 6.31069L17.5677 7.11756C17.9793 7.17679 18.143 7.6834 17.8437 7.97222L13.7892 11.8856L14.7475 17.4175C14.8181 17.8253 14.391 18.1375 14.0239 17.9464L8.99997 15.3311Z" fill="#F8E71C"/>
            </svg>
        </div>
        <p>{{ movie.title }}</p>
        <span>{{ movie.year }}</span>
    </div>
</template>

<script>
export default {
    name: 'MovieCard',
    data() {
        return {
            favorite: this.isFavorite
        }
    },
    props: {
        movie: JSON,
        isFavorite: Boolean
    },
    methods: {
        updateFavorite() {
            this.favorite = !this.favorite
            this.$emit('updated', this.movie.idIMDB)
        }
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

    .card_like {
        position: absolute;
        top: 5px;
        right: 5px;
        cursor: pointer;
    }

    .card_rating:hover {
        opacity: 1;
        transition: all 400ms ease;
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
