<template>
  <section class="main__design" id="ourwork">
    <div class="main__title">
        <h1>{{ titleMainDesign }}</h1>
    </div>
    <div class="main__content-infos">
        <div class="main__infos-design">
            <div :class="item.class" v-for="item in info" :key="item.id">
                <img class="main__img" :src="item.image" :alt="item.alt">
                <p class="main__text-image">{{ item.title }}</p>
                <p class="main__about-image">{{ item.text }}</p>
            </div>
        </div>
    </div>
  </section>
</template>

<script>
    export default {
        name: 'Design',
        data() {
            return {
                titleMainDesign: "Good design means good business",
                info: [
                    {
                        class: "main__content-design down", image: "https://user-images.githubusercontent.com/74377158/192065932-e1aa8372-cf25-4918-8ac4-52d63fb27945.jpg", title: "Full stack application", text: "Smart home dashboard", alt: "smart home"
                    },
                    {
                        class: "main__content-design", image: "https://user-images.githubusercontent.com/74377158/192065931-4fb356e2-d278-4dc2-aefe-ecf2a5e7c679.png", title: "Ux/Ui Design", text: "Onboard application", alt: "onboard"
                    },
                    {
                        class: "main__content-design down", image: "https://user-images.githubusercontent.com/74377158/192065934-918ecde0-1993-44d5-896c-f1e3c947fe94.png", title: "Mobile application", text: "Booking system", alt: "booking"
                    },
                    {
                        class: "main__content-design", image: "https://user-images.githubusercontent.com/74377158/192065928-441e0c0a-5a83-4909-8015-d6b909eac822.png", title: "Front end application", text: "Juice product homepage", alt: "juice product"
                    },
                ]

            }
        }
    }
</script>

<style lang="scss">
    @import '../assets/variables.scss';

    .main {

        &__content-infos {
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        &__infos-design {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 3rem;

            @include for-phone-only {
                grid-template-columns: repeat(1, 1fr);
            }

            @include for-tablet-only {
                grid-template-columns: repeat(1, 1fr);
            }
        }

        &__content-design {
            &.down {
                transform: translateY(75px);

                @include for-phone-only {
                    transform: translateY(0);
                }

                @include for-tablet-only {
                    transform: translateY(0);
                }
            }
        }

        &__img {
            width: 25rem;
            border-radius: 12px;

            @include for-phone-only {
                width: 20rem;
            }
        }

        &__text-image {
            font-size: 14px;
            color: $gray-two;
            line-height: 2.3;
        }

        &__about-image {
            font-size: 20px;

            @include for-phone-only {
                font-size: 18px;
            }
        }
    }

</style>