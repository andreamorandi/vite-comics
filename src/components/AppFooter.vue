<script>
    export default {
        name: "AppFooter",
        data() {
            return {
                logo: "dc-logo-bg.png",
                navigations: [
                    {
                        sectionTitle: "DC COMICS",
                        links: [
                            {
                                linkTitle: "Characters",
                                href: "/characters",
                            },
                            {
                                linkTitle: "Comics",
                                href: "/comics",
                            },
                            {
                                linkTitle: "Movies",
                                href: "/movies",
                            },
                            {
                                linkTitle: "TV",
                                href: "/tv",
                            },
                            {
                                linkTitle: "Games",
                                href: "/games",
                            },
                            {
                                linkTitle: "Videos",
                                href: "/videos",
                            },
                            {
                                linkTitle: "News",
                                href: "/news",
                            },
                        ],
                        subNavigation: {
                            sectionTitle: "SHOP",
                            links: [
                                {
                                    linkTitle: "Shop DC",
                                    href: "/shop",
                                },
                                {
                                    linkTitle: "Shop DC Collectibles",
                                    href: "/collectibles",
                                },
                            ],
                        },
                    },
                    {
                        sectionTitle: "DC",
                        links: [
                            {
                                linkTitle: "Terms Of Use",
                                href: "/terms",
                            },
                            {
                                linkTitle: "Privacy policy (New)",
                                href: "/policy",
                            },
                            {
                                linkTitle: "Ad choices",
                                href: "/ads",
                            },
                            {
                                linkTitle: "Advertising",
                                href: "/adv",
                            },
                            {
                                linkTitle: "Jobs",
                                href: "/jobs",
                            },
                            {
                                linkTitle: "Subscriptions",
                                href: "/subscriptions",
                            },
                            {
                                linkTitle: "Talent Workshops",
                                href: "/workshops",
                            },
                            {
                                linkTitle: "CPSC Certificates",
                                href: "/certificates",
                            },
                            {
                                linkTitle: "Ratings",
                                href: "/ratings",
                            },
                            {
                                linkTitle: "Shop Help",
                                href: "/help",
                            },
                            {
                                linkTitle: "Contact Us",
                                href: "/contact",
                            },
                        ]
                    },
                    {
                        sectionTitle: "SITES",
                        links: [
                            {
                                linkTitle: "DC",
                                href: "/dc",
                            },
                            {
                                linkTitle: "MAD Magazine",
                                href: "/magazine",
                            },
                            {
                                linkTitle: "DC Kids",
                                href: "/kids",
                            },
                            {
                                linkTitle: "DC Universe",
                                href: "/universe",
                            },
                            {
                                linkTitle: "DC Power Visa",
                                href: "/visa",
                            },
                        ]
                    },
                ],
                socials: [
                    {
                        name: "facebook",
                        href: "https://www.facebook.com"
                    },
                    {
                        name: "twitter",
                        href: "https://twitter.com"
                    },
                    {
                        name: "youtube",
                        href: "https://www.youtube.com"
                    },
                    {
                        name: "pinterest",
                        href: "https://www.pinterest.com"
                    },
                    {
                        name: "periscope",
                        href: "https://www.pscp.tv"
                    }
                ],
            };
        },
        methods: {
            getImagePath(imageName) {
                return new URL(`../assets/img/${imageName}`, import.meta.url).href;
            },
        },
    }
</script>

<template>
    <footer>
            <div class="footer-main">
                <div class="container">
                    <div class="nav">
                        <div class="row">
                            <div class="col" v-for="(navigation, index) in navigations" :key="index">
                                <h3>{{ navigation.sectionTitle }}</h3>
                                <ul>
                                    <li v-for="(link,index) in navigation.links" :key="index">
                                        <a :href="link.href"><span>{{ link.linkTitle }}</span></a>
                                    </li>
                                    <template v-if="navigation.subNavigation">
                                        <h3>{{ navigation.subNavigation.sectionTitle }}</h3>
                                        <ul>
                                            <li v-for="(link,index) in navigation.subNavigation.links" :key="index">
                                                <a :href="link.href"><span>{{ link.linkTitle }}</span></a>
                                            </li>
                                        </ul>
                                    </template>
                                </ul>
                            </div>
                        </div>
                    </div>
                    <div class="logo">
                        <img :src="getImagePath(logo)" alt="logo">
                    </div>
                </div>
            </div>
            <div class="footer-cta">
                <div class="container">
                    <div class="sign-up">
                        <a href="/sign-up"><span>SIGN-UP NOW!</span></a>
                    </div>
                    <div class="follow-us">
                        <span>FOLLOW US</span>
                        <a :href="social.href" v-for="(social, index) in socials" :key="index">
                            <img :src="getImagePath(`footer-${social.name}.png`)" :alt="`${social.name} image`">
                        </a>
                    </div>
                </div>
            </div>
    </footer>
</template>

<style lang="scss" scoped>
@use "../styles/partials/mixins" as *;
@use "../styles/partials/variables" as *;

footer {
    .footer-main {
        background-image: url("../assets/img/footer-bg.jpg");
        .container {
            @include flex(row, center, stretch);
            gap: 3rem;
            .nav {
                width: 40%;
                padding: 2rem 0;
                .row {
                    @include flex();
                    align-items: stretch;
                    flex-wrap: wrap;
                    gap: 1.5rem;
                    .col {
                        width: calc(100% / 3 - 1.5rem * 2 / 3);
                        h3 {
                            margin: .75rem 0;
                            color: white;
                        }
                        li {
                            padding: .125rem 0;
                            a {
                                color: lighten(black, 50%);
                                &:hover {
                                    color: $primary-color;
                                }
                            }
                        }
                    }
                }
            }
            .logo {
                width: 60%;
                position: relative;
                overflow: hidden;
                img {
                    position: absolute;
                    top: 50%;
                    right: 0;
                    transform: translateY(-50%);
                }
            }
        }
    }
    .footer-cta {
        padding: 2rem 0;
        background-color: lighten(black, 17.5%);
        .container {
            @include flex();
            .sign-up {
                a {
                    padding: .75rem 1rem;
                    font-weight: 600;
                    border: 2px solid $primary-color;
                    color: white;
                    &:hover {
                        color: black;
                        background-color: $primary-color;
                    }
                }
            }
            .follow-us {
                @include flex();
                * {
                    margin: 0rem .25rem;
                }
                span {
                    font-size: 1.25rem;
                    font-weight: 600;
                    margin-right: .5rem;
                    color: $primary-color;
                }
            }
        }
    }
}

</style>