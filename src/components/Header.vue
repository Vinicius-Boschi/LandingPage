<template>
      <header class="header" id="home">
        <div class="header__container">
            <nav class="header__navbar" role="navigation">
                <div class="header__action">
                    <h1 class="header__title">{{ titleHeader }}</h1>
                    <button class="header__button">
                        <i class="fa-solid fa-bars-staggered"></i>
                    </button>
                </div>
                <div class="header__links-container">
                    <ul class="header__lists">
                        <li v-for="item in content" :key="item.id">
                            <a :href="item.link">{{ item.name }}</a>
                        </li>
                    </ul>
                </div>
            </nav>
        </div>
    </header>
</template>

<script>
    export default {
        name: 'Header',
        data() {
            return {
                titleHeader: "Edie",
                content: [
                    { name: 'Home', link: '#home' },
                    { name: 'Services', link: '#services' },
                    { name: 'OurWorks', link: '#ourwork' },
                    { name: 'Clients', link: '#clients' },
                    { name: 'Contact', link: '#' }
                ]
            }
        },
        methods: {
            responsiveNav() {
                const button = document.querySelector('.header__button')
                const linksContainer = document.querySelector('.header__links-container')
                const links = document.querySelector('.header__lists')
                
                button.addEventListener('click', () => {
                    const height = linksContainer.getBoundingClientRect().height
                    const linksHeight = links.getBoundingClientRect().height

                    if (height === 0) {
                        linksContainer.style.height = `${linksHeight}px`
                    } else {
                        linksContainer.style.height = 0
                    }
                })
            }
        },
        mounted() {
            this.responsiveNav()
        }
    }
</script>

<style lang="scss">
    @import '../assets/variables.scss';

    .header {

        &__navbar {
            display: flex;
            justify-content: space-around;
            align-items: center;
            padding: 2rem;

            @include for-phone-only {
                display: block;
            }

            @include for-tablet-only {
                display: block;
            }
        }

        &__action {
            display: flex;
            justify-content: space-between;
        }

        &__title {
            color: $gray;
            font-family: $font-two;
            font-weight: 800;
            font-size: 32px;
        }

        &__button {
            display: none;
            background: transparent;
            border-color: transparent;
            cursor: pointer;
            font-size: 20px;

            @include for-phone-only {
                display: block;
            }

            @include for-tablet-only {
                display: block;
            }
        }

        &__links-container {
            transition: all 3s linear;

            @include for-phone-only {
                overflow: hidden;
                height: 0;
            }

            @include for-tablet-only {
                overflow: hidden;
                height: 0;
            }
        }

        &__lists {
            display: flex;
            font-size: 20px;
            font-weight: 500;
            letter-spacing: 2px;

            li {
                padding: 1rem;
            }

            a {
                position: relative;

                &::before {
                    content: '';
                    position: absolute;
                    width: 100%;
                    height: 3px;
                    bottom: 0;
                    left: 0;
                    background-color: black;
                    visibility: hidden;
                    transform: scaleX(0);
                    transition: all 0.3s ease-in-out 0s;
                }

                &:hover::before {
                    visibility: visible;
                    transform: scaleX(1);
                }
            }

            @include for-phone-only {
                display: block;
            }

            @include for-tablet-only {
                display: block;
            }
        }
    }
</style>