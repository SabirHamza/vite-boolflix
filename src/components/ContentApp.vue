<script>
export default {
    data() {
        return {
            apiflags: "https://countryflagsapi.com/png/BR"
        }
    },

    props: {
        imgpath: String,
        originaltitle: String,
        title: String,
        vote: Number,
        language: String
    }
}
</script>

<template>
    <div class="col-2 py-2">
        <div class="poster">
            <img class="img-fluid" :src="'https://image.tmdb.org/t/p/w342' + imgpath" alt="">
        </div>
        <img src="" alt="">
        <h5>{{ title }}</h5>
        <span>{{ Math.floor(vote) }}</span>
    </div>
</template>

<style lang="scss" scoped></style>