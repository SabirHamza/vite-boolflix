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
            <div class="row">
                <h3>MOVIE</h3>
                <ContentApp v-for="content in store.movie" :imgpath="content.poster_path" :title="content.title"
                    :originaltitle="content.original_title" :vote="content.vote_average"
                    :language="content.original_language" />
            </div>
            <div class="row">
                <h3>TV SHOW</h3>
                <ContentApp v-for="content in store.tvshow" :imgpath="content.poster_path" :title="content.title"
                    :originaltitle="content.original_title" :vote="content.vote_average"
                    :language="content.original_language" />
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped></style>