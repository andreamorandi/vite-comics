<script>
export default {
    name: "ComicCard",
    props: {
        title: String,
        imgSrc: String
    }
}
</script>

<template>
    <div class="card">
        <div class="img-wrapper">
            <img :src="imgSrc" :alt="`${title} image`">
        </div>
        <p>{{ title }}</p>
    </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/mixins" as *;
@use "../styles/partials/variables" as *;

.card {
    width: calc(80vw / 6 - 1.5rem / 5 * 6);
    .img-wrapper {
        height: calc(80vw / 6 - 1.5rem / 5 * 6);
        overflow: hidden;
        img {
            display: block;
        }
    }
    p {
        margin-top: .5rem;
        text-transform: uppercase;
        color: white;
    }
}

</style>