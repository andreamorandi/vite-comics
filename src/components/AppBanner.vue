<script>
    export default {
        name: "AppBanner",
        data() {
            return {
                features: [
                    {
                        description: "DIGITAL COMICS",
                        image: "buy-comics-digital-comics.png",
                        href: "/dc"
                    },
                    {
                        description: "DC MERCHANDISE",
                        image: "buy-comics-merchandise.png",
                        href: "/merchandise"
                    },
                    {
                        description: "SUBSCRIPTION",
                        image: "buy-comics-subscriptions.png",
                        href: "/subscriptions"
                    },
                    {
                        description: "COMIC SHOP LOCATOR",
                        image: "buy-comics-shop-locator.png",
                        href: "/locator"
                    },
                    {
                        description: "DC POWER VISA",
                        image: "buy-dc-power-visa.svg",
                        href: "/visa"
                    },
                ],
            };
        },
        methods: {
            getImagePath(imageName) {
                return new URL(`../assets/img/${imageName}`, import.meta.url).href;
            },
        },
    };
</script>

<template>
    <div class="banner">
        <div class="container">
            <div class="row">
                <div class="col" v-for="(feature, index) in features" :key="index">
                    <a :href="feature.href">
                        <img :src="getImagePath(feature.image)" :alt="`${feature.description} IMAGE`">
                        <span class="image-description">{{ feature.description }}</span>
                    </a>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/mixins" as *;
@use "../styles/partials/variables" as *;

.banner {
    background-color: $primary-color;
    .container {
        .row {
            width: 100%;
            height: 100%;
            @include flex();
            gap: 1rem;
            .col {
                width: calc(100% / 5 - 1rem * 4 / 5);
                padding: 2.5rem 0;
                a {
                    @include flex-center();
                    gap: .5rem;
                    transition: transform .25s;
                    img {
                        width: 45px;
                    }
                    .image-description {
                        font-size: .9rem;
                        color: white;
                        
                    }
                    &:hover {
                        transform: scale(1.25);
                    }
                }
            }
            .col:nth-child(4) img {
                width: 30px;
            }
        }
    }
}
</style>