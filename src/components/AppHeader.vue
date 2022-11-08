<script>
    export default {
        name: "AppHeader",
        data() {
            return {
                logo: "dc-logo.png",
                links: [
                    {
                        title: "CHARACTERS",
                        href: "/characters",
                        active: false,
                    },
                    {
                        title: "COMICS",
                        href: "/comics",
                        active: true,
                    },
                    {
                        title: "MOVIES",
                        href: "/movies",
                        active: false,
                    },
                    {
                        title: "TV",
                        href: "/tv",
                        active: false,
                    },
                    {
                        title: "GAMES",
                        href: "/games",
                        active: false,
                    },
                    {
                        title: "COLLECTIBLES",
                        href: "/collectibles",
                        active: false,
                    },
                    {
                        title: "VIDEOS",
                        href: "/videos",
                        active: false,
                    },
                    {
                        title: "FANS",
                        href: "/fans",
                        active: false,
                    },
                    {
                        title: "NEWS",
                        href: "/news",
                        active: false,
                    },
                    {
                        title: "SHOP",
                        href: "/shop",
                        active: false,
                    },
                ]
            }
        },
        methods: {
            getImagePath(imageName) {
                return new URL(`../assets/img/${imageName}`, import.meta.url).href;
            }
        },
    }
</script>

<template>
    <header>
        <div class="logo">
            <img :src="getImagePath(logo)" alt="">
        </div>
        <nav class="header-navigation">
            <ul>
                <li v-for="(link, index) in links" :key="index">
                    <a :class="{ 'active': link.active }" :href="link.href">{{ link.title }}</a>
                </li>
            </ul>
        </nav>
    </header>
</template>

<style lang="scss" scoped>
@use "../styles/partials/mixins" as *;
@use "../styles/partials/variables" as *;

header {
    // debug
    background-color: grey;

    height: 6rem;
    @include flex();
    .logo {
        width: 20%;
        height: 100%;
        @include flex(row, center, center);
        img {
            height: 80%;
        }
    }
    .header-navigation {
        width: 65%;
        height: 100%;
        ul {
            height: 100%;
            @include flex();
            padding-right: 15%;
        }
        li {
        // debug
        border-bottom: 5px solid $primary-color;

        height: 100%;
        @include flex-center();
            a {
                font-size: .8rem;
            }
        }
    }
    
}
</style>