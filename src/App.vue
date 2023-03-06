<script>
import axios from 'axios'
import { store } from './data/store'
import HeaderApp from './components/HeaderApp.vue'
import MainApp from './components/MainApp.vue'

export default {
  data() {
    return {
      store,

      baseuri: 'https://api.themoviedb.org/3/search/movie?api_key=3079dda23a46fd872b07be86b8f57c67'
    }
  },

  created() {
  },

  methods: {
    showcontent(content) {
      this.baseuri += `&query=${content}`

      console.log(this.baseuri);

      axios
        .get(this.baseuri)
        .then((response) => {
          store.movie = response.data.results

          console.log(response);

          console.log(store.movie);
        })
    }
  },

  components: { HeaderApp, MainApp }
}
</script>

<template>
  <HeaderApp @searchcontent="showcontent" />
  <MainApp />
</template>

<style scoped></style>
