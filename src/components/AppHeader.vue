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
        <div class="container">
            <div class="logo">
                <a href="/comics">
                    <img :src="getImagePath(logo)" alt="">
                </a>
            </div>
            <nav class="header-navigation">
                <ul>
                    <li v-for="(link, index) in links" :key="index">
                        <a :class="{ 'active': link.active }" :href="link.href"><span>{{ link.title }}</span></a>
                    </li>
                </ul>
            </nav>
        </div>
    </header>
</template>

<style lang="scss" scoped>
@use "../styles/partials/mixins" as *;
@use "../styles/partials/variables" as *;

header {
    // debug
    background-color: grey;
    .container {
        height: 6rem;
        @include flex();
        .logo {
            height: 100%;
            flex-shrink: 0;
            a {
                height: 100%;
                @include flex(row, center, center);
                img {
                    height: 80%;
                }
            }
        }
        .header-navigation {
            height: 100%;
            ul {
                height: 100%;
                @include flex();
                li {
                    height: 100%;
                    a {
                        height: 100%;
                        @include flex-center();
                        font-size: .85rem;
                        font-weight: 600;
                        padding: 0rem 1rem;
                        border-bottom: 5px solid transparent;
                        &:hover,
                        &.active {
                            border-bottom: 5px solid $primary-color;
                        }
                    }
                }
            }
        }
    }
    
}
</style>