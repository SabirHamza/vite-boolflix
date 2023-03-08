<script>
import axios from 'axios'
import { store } from './data/store'
import HeaderApp from './components/HeaderApp.vue'
import MainApp from './components/MainApp.vue'

export default {
  data() {
    return {
      store,

      baseurimovie: 'https://api.themoviedb.org/3/search/movie?api_key=3079dda23a46fd872b07be86b8f57c67',

      baseuritv: 'https://api.themoviedb.org/3/search/tv?api_key=3079dda23a46fd872b07be86b8f57c67'
    }
  },

  created() {
  },

  methods: {

    showmovie(content) {
      this.baseurimovie += `&query=${content}`

      axios
        .get(this.baseurimovie)
        .then((response) => {
          store.movie = response.data.results

          console.log(response);

          console.log(store.movie);
        })
    },

    showtv(content) {
      this.baseuritv += `&query=${content}`

      axios
        .get(this.baseuritv)
        .then((response) => {
          store.tvshow = response.data.results

          console.log(response);

          console.log(store.tvshow);
        })
    },

    showcontent(content) {
      this.showmovie(content)
      this.showtv(content)
    },

  },

  components: { HeaderApp, MainApp }
}
</script>

<template>
  <HeaderApp @searchcontent="showcontent" />
  <MainApp />
</template>

<style scoped></style>
