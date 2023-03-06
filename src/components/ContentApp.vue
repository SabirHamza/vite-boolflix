<script>
export default {
    data() {
        return {
        }
    },

    props: {
        imgpath: String,
        originaltitle: String,
        title: String,
        vote: String,
        language: String
    }
}
</script>

<template>
    <div>
        <div class="poster">
            <strong>BOOLFLIX</strong>
            <img src="" alt="">
        </div>
        <span>{{ language }}</span>
        <h5>{{ title }}</h5>
        <span>{{ Math.floor(vote) }}</span>
    </div>
</template>

<style lang="scss" scoped>
.poster {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 200px;
    color: midnightblue;
    border: 5px solid midnightblue;
}
</style>