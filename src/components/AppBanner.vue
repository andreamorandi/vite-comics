<script>
    export default {
        name: "AppBanner",
        data() {
            return {
                images: [
                    {
                        name: "buy-comics-digital-comics.png",
                        description: "DIGITAL COMICS"
                    },
                    {
                        name: "buy-comics-merchandise.png",
                        description: "DC MERCHANDISE"
                    },
                    {
                        name: "buy-comics-subscriptions.png",
                        description: "SUBSCRIPTION"
                    },
                    {
                        name: "buy-comics-shop-locator.png",
                        description: "COMIC SHOP LOCATOR"
                    },
                    {
                        name: "buy-dc-power-visa.svg",
                        description: "DC POWER VISA"
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
                <div class="col" v-for="(image, index) in images" :key="index">
                    <img :src="getImagePath(image.name)" :alt="`${image.description} IMAGE`">
                    <span class="image-description">{{ image.description }}</span>
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
                @include flex-center();
                gap: .5rem;
                padding: 2.5rem 0;
                img {
                    width: 45px;
                }
                .image-description {
                    font-size: .9rem;
                    color: white;
                    
                }
            }
            .col:nth-child(4) img {
                width: 30px;
            }
        }
    }
}
</style>