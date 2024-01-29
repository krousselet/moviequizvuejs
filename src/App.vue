<template>
  <header>
    <Navbar :pages="pages" :activePage="activePage" :dropdowns="dropdowns"></Navbar>
  </header>
</template>

<script>
import Navbar from './components/Navbar.vue'

export default {
  name: 'App',
  components: {
    Navbar,
  },
  data() {
    return {
      activePage: 0,
      dropdowns: [
        {
          link: {
            url: '',
            content: 'Rules',
            title: 'This link goes to ',
          }
        },
      ],
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
      ]
    }
  },
}
</script>

<style scoped></style>
