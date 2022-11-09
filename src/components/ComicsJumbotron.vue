<script>
export default {
    name: "ComicsJumbotron",
};
</script>

<template>
    <div class="jumbotron"></div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/mixins" as *;
@use "../styles/partials/variables" as *;
.jumbotron {
    width: 100%;
    padding: 15rem 0;
    background-image: url("../assets/img/jumbotron.jpg");
    background-size: cover;
}
</style>