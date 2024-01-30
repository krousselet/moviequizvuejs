<template>
    <div class="swiper">
        <div class="swiper-wrapper">
            <div class="swiper-slide" v-for="(movie, movieIndex) in allMovies" :key="movieIndex"
                @click="selectMovie(movie)">
                <img :src="movie.url" :alt="movie.title">
            </div>
        </div>
        <div class="swiper-pagination"></div>
        <div class="swiper-button-prev"></div>
        <div class="swiper-button-next"></div>
        <div class="swiper-scrollbar"></div>
    </div>
    <div class="swiper">
        <div class="swiper-wrapper">
            <div class="swiper-slide" v-for="(serie, serieIndex) in allSeries" :key="serieIndex"
                @click="selectSerie(serie)">
                <img :src="serie.url" :alt="serie.title">
            </div>
        </div>
        <div class="swiper-pagination"></div>
        <div class="swiper-button-prev"></div>
        <div class="swiper-button-next"></div>
        <div class="swiper-scrollbar"></div>
    </div>
</template>

<script>
export default {
    props: ['games'],
    emits: ['movie-selected', 'serie-selected'],
    methods: {
        selectMovie(movie) {
            this.$emit('movie-selected', movie);
        },
        selectSerie(serie) {
            this.$emit('serie-selected', serie);
        },
    },
    computed: {
        allMovies() {
            return this.games.flatMap(game => game.movies);
        },
        allSeries() {
            return this.games.flatMap(game => game.series);
        },
    },
    mounted() {
        this.swiper = new Swiper('.swiper', {
            direction: 'horizontal',
            loop: true,
            slidesPerView: 1,
            breakpoints: {
                580: {
                    slidesPerView: 3
                },
                992: {
                    slidesPerView: 6
                }
            },

            pagination: {
                el: '.swiper-pagination',
            },

            navigation: {
                nextEl: '.swiper-button-next',
                prevEl: '.swiper-button-prev',
            },


            scrollbar: {
                el: '.swiper-scrollbar',
            },
        })
    },
}
</script>

<style scoped>
.test {
    background-size: cover;
    background-position: center;
}

img {
    width: fit-content;
    height: fit-content;
}
</style>