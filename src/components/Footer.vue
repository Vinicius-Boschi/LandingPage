<template>
  <footer class="footer">
        <div class="footer__content">
            <div class="footer__lists">
            <ul class="footer__list">
                <li v-for="item in links" :key="item.id">
                    <a :href="item.link">{{ item.name }}</a>
                </li>
            </ul>
        </div>
        <div class="footer__media">
            <span class="footer__name">{{ footerName }}</span>
            <ul class="footer__social">
                <li v-for="media in socialMedia" :key="media.id">
                    <a :href="media.link">
                        <i :class="media.class"></i>
                    </a>
                </li>
            </ul>
        </div>
    </div>
    <div class="footer__created">
        <p>{{ createdBy }} <span><a :href="linkGithub" target="_blank">{{ nameAuthor }}</a></span> - {{ enterprise }}</p>
    </div>
  </footer>
</template>

<script>
    export default {
        name: 'Footer',
        data() { 
            return {
                footerName: "Edie",
                createdBy: "created by",
                linkGithub: "https://github.com/Vinicius-Boschi",
                nameAuthor: "Vinícius Boschi",
                enterprise: "devChallenges.io",
                links: [
                    { name: 'Home', link: '#home' },
                    { name: 'Services', link: '#services' },
                    { name: 'Our Works', link: '#ourworks' },
                    { name: 'Client', link: '#client' },
                    { name: 'Contact', link: '#contact' }
                ],
                socialMedia: [
                    { class: 'fa-brands fa-instagram', link: '#' },
                    { class: 'fa-brands fa-linkedin', link: '#' },
                    { class: 'fa-brands fa-twitter', link: '#' }
                ]
            }
        }
    }
</script>

<style lang="scss">
    @import '../assets/variables.scss';

    .footer {
        background-color: $darkBlue;
        height: 15rem;
        color: $light-gray;
        padding: 1rem;

        @include for-phone-only {
            width: calc(100% - 32px);
        }

        @include for-tablet-only {
            width: calc(100% - 32px);
        }

        &__content {
            display: flex;
            justify-content: space-evenly;
            align-items: center;
        }

        &__lists {
            line-height: 2;

            a {
                position: relative;

                &::before {
                    content: '';
                    position: absolute;
                    width: 100%;
                    height: 3px;
                    bottom: 0;
                    left: 0;
                    background-color: $light-gray;
                    visibility: hidden;
                    transform: scaleX(0);
                    transition: all 0.3s ease-in-out 0s;
                }

                &:hover::before {
                    visibility: visible;
                    transform: scaleX(1);
                }
            }
        }

        &__name {
            font-size: 32px;
            font-weight: 800;
        }

        &__social {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;

            i {
                font-size: 24px;
            }
        }

        &__created {
            text-align: center;
            padding: 2rem;

            span {
                font-weight: 800;
            }
        }
    }

</style>