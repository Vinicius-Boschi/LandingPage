<template>
    <section class="main__services" id="services">
        <div class="main__title">
            <h1>{{ titleMain }}</h1>
        </div>
        <div class="main__content">
            <div class="main__cards" v-for="item in content" :key="item.id">
                <i :class="item.fontAwesome" :id="item.IDicon"></i>
                <h2 class="main__title-card">{{ item.title }}</h2>
                <p class="main__text-card">{{ item.text }}</p>
                <button class="main__button">{{ item.textButton }}</button>
            </div>
        </div>
    </section>
</template>

<script>
    export default {
        name: 'Services',
        data() {
            return {
                titleMain: "We offer high demand services",
                content: [
                    {
                        fontAwesome: "fa-solid fa-pen", IDicon: "iconBlue", title: "Ux/Ui Design", text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis a metus ac nulla consequat aliquet id quis turpis.", textButton: "Get Started"
                    },
                    {
                        fontAwesome: "fa-solid fa-code", IDicon: "iconGreen", title: "Front end", text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis a metus ac nulla consequat aliquet id quis turpis.", textButton: "Get Started"
                    },
                    {
                        fontAwesome: "fa-solid fa-server", IDicon: "iconRed", title: "Back end", text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis a metus ac nulla consequat aliquet id quis turpis.", textButton: "Get Started"
                    }
                ]
            }
        }
    }
</script>

<style lang="scss">
    @import '../assets/variables.scss';

    .main {

        &__title {
            h1 {
                font-weight: 500;
                font-size: 36px;
                width: 28%;
                line-height: 1.3;

                @include for-phone-only {
                    width: auto;
                    margin-bottom: 1rem;
                    font-size: 30px;
                }

                @include for-tablet-only {
                    width: 80%;
                    margin-bottom: 1rem;
                }
            }
        }

        &__content {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            padding: 2rem;

            @include for-phone-only {
                grid-template-columns: repeat(1, 1fr);
                justify-content: center;
            }

            @include for-tablet-only {
                grid-template-columns: repeat(1, 1fr);
                justify-content: center;
            }
        }

        &__cards {
            line-height: 1.5;
            width: calc(100% - 150px);
            padding: 2rem;
            transition: all .3s linear;

            i {
                color: $light-gray;
            }

            #iconBlue, #iconGreen, #iconRed {
                background-color: $blue;
                padding: 1rem;
                border-radius: 8px;
            }

            #iconGreen {
                background-color: $green;
            }

            #iconRed {
                background-color: $red;
            }

            &:hover {
                background: #FFFFFF;
                box-shadow: 0px 10px 30px rgba(51, 51, 51, 0.1);
                border-radius: 24px;
            }

            @include for-phone-only {
                width: 70%;
            }

            @include for-tablet-only {
                width: 70%;
            }
        }

        &__title-card {
            font-weight: 700;
            font-size: 24px;
            margin: 1rem 0rem 1rem 0rem;
        }

        &__text-card {
            width: 270px;
            font-weight: 400;
            font-size: 15px;
            margin-bottom: 1rem;
        }
    }

</style>