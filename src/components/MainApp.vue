<script>
import { store } from '../data/store'
import ContentApp from './ContentApp.vue'

export default {
    data() {
        return {
            store,
        }
    },

    components: { ContentApp }
}

</script>

<template>
    <main>
        <div class="container">
            <h3 v-if="!store.movie.length">Inserisci titolo del contenuto</h3>
            <div class="row">
                <h3 v-if="store.movie.length">MOVIE</h3>
                <ContentApp v-for="content in store.movie" :imgpath="content.poster_path" :title="content.title"
                    :originaltitle="content.original_title" :vote="content.vote_average"
                    :language="content.original_language" />
            </div>
            <div class="row">
                <h3 v-if="store.movie.length">TV SHOW</h3>
                <ContentApp v-for="content in store.tvshow" :imgpath="content.poster_path" :title="content.title"
                    :originaltitle="content.original_title" :vote="content.vote_average"
                    :language="content.original_language" />
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped></style>