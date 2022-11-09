<script>
import ComicsJumbotron from "./ComicsJumbotron.vue";
import ComicsList from "./ComicsList.vue";

export default {
    name: "AppContent",
    components: {
        ComicsJumbotron,
        ComicsList
    },
};
</script>

<template>
    <main>
        <ComicsJumbotron />
        <ComicsList />
    </main>
</template>

<style lang="scss" scoped>
@use "../styles/partials/mixins" as *;
@use "../styles/partials/variables" as *;
main {
    background-color: lighten(black, 10%);
    .container {
        p {
            font-size: 1.2rem;
            font-weight: 700;
            padding: 2.5rem 0;
            color: white;
        }
    }
}
</style>