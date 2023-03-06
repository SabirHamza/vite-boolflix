<script>
import { store } from '../data/store'

export default {
    data() {
        return {
            store,

            content: ""
        }
    },

    emits: ['searchcontent'],

    methods: {

        search() {
            console.log(this.content);

            this.$emit('searchcontent', this.content)
        },

        reset() {
            this.content = ""

            this.$emit('searchcontent', this.content)
        }
    }
}
</script>

<template>
    <header>
        <nav class="navbar">
            <div class="container">
                <a class="navbar-brand fw-bold text-danger">BOOLFLIX</a>
                <form @submit.prevent="" class="d-flex" role="search">
                    <input class="form-control me-2" @keyup.enter="search()" @click="reset()" v-model="content" type=""
                        placeholder="">
                    <button class="btn  btn-outline-danger" @click="search()" type="button">Search</button>
                </form>
            </div>
        </nav>
    </header>
</template>

<style lang="scss" scoped>
header {
    position: fixed;
    width: 100%;
    background-color: white;
}
</style>
