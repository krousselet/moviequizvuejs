<template>
  <header>
    <Navbar :pages="pages" :activePage="activePage" :dropdowns="dropdowns"></Navbar>
  </header>
  <main class="main">
    <MovieGuessForm v-if="selectedMovie" :movie="selectedMovie" :activeFormMovie=1></MovieGuessForm>
    <SerieGuessForm v-if="selectedSerie" :serie="selectedSerie" :activeFormSerie=1></SerieGuessForm>
    <Swiper v-if="activePage === 0" :games="games" @movieSelected="handleMovieSelect" @serieSelected="handleSerieSelect">
    </Swiper>

  </main>
</template>

<script>
import Navbar from './components/Navbar.vue';
import Swiper from './components/Swiper.vue';
import MovieGuessForm from './components/MovieGuessForm.vue';
import SerieGuessForm from './components/SerieGuessForm.vue';

export default {
  name: 'App',
  components: {
    Navbar,
    Swiper,
    MovieGuessForm,
    SerieGuessForm
  },
  data() {

    return {
      activePage: 0,
      activeFormMovie: 0,
      activeFormSerie: 0,
      //********************** NAVBAR DROPDOWNS ******************************/
      dropdowns: [
        {
          link: {
            url: '',
            content: 'Rules',
            title: 'This link goes to ',
          }
        },
      ],
      //********************** NAVBAR ******************************/
      pages: [
        {
          link: {
            url: '',
            content: 'Home',
            title: 'This link goes to ',
          }
        },
        {
          link: {
            url: '',
            content: 'About',
            title: 'This link goes to ',
          }
        },
        {
          link: {
            url: '',
            content: 'Contact',
            title: 'This link goes to ',
          }
        },
      ],

      //************************* SWIPER DATA **********************************/
      games: [
        {
          movies: [
            {
              url: 'https://media.vanityfair.fr/photos/6426aa2f26a0c074c81a3937/16:9/w_2560%2Cc_limit/GettyImages-156473199.jpg',
              title: 'Gladiator',
              description: '',
            },
            {
              url: 'https://movieplayer.net-cdn.it/t/images/2023/05/26/pearl-harbor_jpg_1600x900_crop_q85.jpg',
              title: 'Pearl Harbor',
              description: '',
            },
            {
              url: 'https://www.usatoday.com/gcdn/-mm-/2abc4a8ff8153af3327de4720edcf8a76bc28036/c=302-0-1441-856/local/-/media/USATODAY/USATODAY/2014/08/06/1407371057000-XXX-TEENAGE-MUTANT-NINJA-TURTLES-MOV-JY-1478--66316298.JPG',
              title: 'Ninja Turtles',
              description: '',
            },
            {
              url: 'https://i0.wp.com/theartofcostume.com/wp-content/uploads/2021/10/nightmare-on-elm-street-movies-in-order-index-1632944846.jpeg?fit=1024%2C514&ssl=1',
              title: 'Freddy',
              description: '',
            },
          ],
          series: [
            {
              url: 'https://leclaireur.fnac.com/wp-content/uploads/2023/09/totally-spies-1256x720.jpg',
              title: 'Totaly Spies',
              description: '',
            },
            {
              url: 'https://i.insider.com/5956abe5b4db9bea5b8b4968?width=700',
              title: 'Charmed',
              description: '',
            },
            {
              url: 'https://media.wired.com/photos/5955beec63d43b038e9bc7be/master/pass/Agents-of-SHIELD.jpg',
              title: 'Agents of Shield',
              description: '',
            },
            {
              url: 'https://resizing.flixster.com/-XZAfHZM39UwaGJIFWKAE8fS0ak=/v3/t/assets/p11408531_i_v8_aa.jpg',
              title: 'Daredevil',
              description: '',
            },
          ],
        }
      ],
      //************************ DISPLAY MOVIE/SERIE ************************/
      selectedMovie: null,
      selectedSerie: null,

    }
  },
  methods: {
    handleMovieSelect(movie) {
      this.selectedMovie = movie;
    },
    handleSerieSelect(serie) {
      this.selectedSerie = serie;
    },
  }
}
</script>

<style>
body {
  background-color: black;
}
</style>
