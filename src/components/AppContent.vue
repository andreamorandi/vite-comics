<script>
    export default {
        name: "AppContent"
    }
</script>

<template>
    <div class="content">
        <div class="container">
            <p>--> Content goes here &lt--</p>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/mixins" as *;
@use "../styles/partials/variables" as *;
.content {
    background-color: lighten(black, 10%);
    .container {
        height: 6rem;
        @include flex-center("vertical");
        p {
            font-size: 1.2rem;
            font-weight: 700;
            color: white;
        }
    }
}
</style>