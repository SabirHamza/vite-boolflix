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
                <div v-for="content in store.movie" class="col-2">
                    <ContentApp :imgpath="content.backdrop_path" :title="content.title"
                        :originaltitle="content.original_title" :vote="content.vote_average"
                        :language="content.original_language" />
                </div>
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
main {
    padding-top: 100px;
}
</style>