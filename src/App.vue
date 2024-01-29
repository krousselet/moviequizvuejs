<template>
  <header>
    <NavbarMobile :pages="pages" :activePage="activePage"></NavbarMobile>
  </header>
</template>

<script>
import NavbarMobile from './components/NavbarMobile.vue'

export default {
  name: 'App',
  components: {
    NavbarMobile,
  },
  data() {
    return {
      activePage: 0,
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
