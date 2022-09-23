<template>
  <section class="main__team" id="clients">
    <div class="main__content-team">
        <div class="main__text">
            <h3>Meet the team</h3>
            <h1 class="main__title-h1">We are chilled and a laidback team</h1>
            <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit.</p>
        </div>
        <div class="main__team-people">
            <div>
                <img src="https://user-images.githubusercontent.com/74377158/192065708-f71b6d6e-4f7d-430b-91b6-c0030645f542.png" alt="person 3">
            </div>
            <div class="main__column">
                <img src="https://user-images.githubusercontent.com/74377158/192065704-9df1c814-682a-43cb-b2e3-feb048a37a60.png" alt="person 1">
                <img src="https://user-images.githubusercontent.com/74377158/192065706-80b40376-b637-4479-90ba-ed855e6ea62d.png" alt="person 2">
            </div>
        </div>
    </div>
    <div class="main__writter">
        <h1 class="main__text-writter">“Fast and outstanding resutls. Edie understands their customer’s needs. They have a young and talented team.”</h1>
    </div>
    <div class="main__author">
        <img src="https://user-images.githubusercontent.com/74377158/192065703-0a196272-2d06-48ea-8fc9-57399df6b7f7.png" alt="person 4">
        <div class="main__info-author">
            <span class="main__name">Carlos Trans</span>
            <span class="main__subtitle">The decorate gatsby</span>
        </div>
    </div>

  </section>
</template>

<script>
    export default {
        name: 'Team'
    }
</script>   

<style lang="scss">
    @import '../assets/variables.scss';

    .main {

        &__content-team {
            display: flex;
            justify-content: center;
            align-items: center;
            margin-top: 3rem;

            @include for-phone-only {
                flex-direction: column;
            }

            @include for-tablet-only {
                flex-direction: column;
            }
        }

        &__text {
            line-height: 1.3;

            h3 {
                color: $red;
                font-size: 16px;
            }

            h1 {
                font-weight: 500;
                font-size: 36px;
                width: 50%;

                @include for-phone-only {
                    width: auto;
                    font-size: 30px;
                }

                @include for-tablet-only {
                    width: auto;
                }
            }

            p {
                font-size: 16px;
                font-weight: 400;
                width: 40%;
                line-height: 1.3;

                @include for-phone-only {
                    width: auto;
                    margin-bottom: 2rem;
                }

                @include for-tablet-only {
                    width: auto;
                    margin-bottom: 2rem;
                }
            }
        }

        &__team-people {
            display: flex;
            align-items: center;
            gap: 2rem;

            img {
                width: 13rem;
                border-radius: 24px;

                @include for-phone-only {
                    width: 8rem;
                }

                @include for-tablet-only {
                    width: 10rem;
                }
            }
        }

        &__column {
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }

        &__writter {
            margin-bottom: 2rem;
        }

        &__text-writter {
            font-weight: 500;
            font-size: 28px;
            width: 50%;
            line-height: 1.3;

            @include for-phone-only {
                width: auto;
                margin-top: 2rem;
                font-size: 22px;
            }

            @include for-tablet-only {
                width: auto;
                margin-top: 2rem;
            }
        }

        &__author {
            display: flex;
            align-items: center;
            
            img {
                width: 4rem;
                height: 4rem;
                border-radius: 24px;
            }
        }

        &__info-author {
            display: flex;
            flex-direction: column;
            gap: 1rem;
            padding: 1rem;
        }

        &__name {
            font-weight: bold;
        }

        &__subtitle {
            color: $gray;
            font-size: 14px;
        }
    }

</style>