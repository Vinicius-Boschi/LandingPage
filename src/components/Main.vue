<template>
  <main class="main">
    <section class="main__section">
        <div class="main__infos">
            <div class="main__smallTitle">
                <h1>Unhappy with your website?</h1>
            </div>
            <h2>We create beautiful and fast web services</h2>
            <img class="main__infos-img" src="https://user-images.githubusercontent.com/74377158/192065635-628e322e-6f8b-465b-9e4e-f4448378db5f.jpg" alt="meeting picture">
            <h2>Story, emotion and purpose</h2>
            <p class="main__paragraph">We help transform your ideas into real world applications that will outperform your toughest competition and help you achieve your strategic goals in short period of time.</p>
            <form action="#" class="main__form">
                <label for="text" class="main__label">Want us contact you?</label>
                <input class="main__input" type="email" name="email" id="email" placeholder="Email">
                <button class="main__button" type="submit">Join</button>
            </form>
        </div>
    </section>
    <Services />
    <Design />
    <Team />
  </main>
</template>

<script>
    import Services from './Services.vue'
    import Design from './Design.vue'
    import Team from './Team.vue'

    export default {
        name: 'Main',
        components: {
            Services,
            Design,
            Team
        }
    }
</script>

<style lang="scss">
    @import '../assets/variables.scss';

    .main {
        margin: 2rem;
        padding: 2rem;

        &__section {
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        &__smallTitle {
            color: $blue;
            font-weight: 500;
            font-size: 15px;
            margin: 1rem;
        }

        &__infos {
            h2 {
                font-weight: 500;
                font-size: 42px;
                width: 35%;
                line-height: 1.2;
                margin: 1rem;

                @include for-phone-only {
                    width: auto;
                    font-size: 30px;
                }

                @include for-tablet-only {
                    width: auto;
                }
            }

            &-img {
                border-radius: 18px;
                width: calc(100% - 100px);

                @include for-phone-only {
                    width: 22rem;
                    height: 8rem;
                }

                @include for-tablet-only {
                    width: 32rem;
                    height: 12rem;
                }
            }
        }

        &__paragraph {
            font-size: 15px;
            font-weight: 400;
            width: 25%;
            margin: 2rem 0 2rem 1rem;
            line-height: 27px;

            @include for-phone-only {
                width: auto;
            }
            
            @include for-tablet-only {
                width: auto;
            }
        }

        &__form {
            margin-left: 1rem;
            margin-bottom: 5rem;
        }

        &__label {
            display: flex;
            margin-bottom: 1rem;
            font-size: 14px;
        }

        &__input {
            width: 350px;
            padding: 1rem;
            margin-right: 1rem;
            background-color: $light-gray;
            border-radius: 12px;
            border: none;

            @include for-phone-only {
                width: auto;
            }

            @include for-tablet-only {
                width: auto;
            }
        }

        &__button {
            width: 100px;
            height: 40px;
            border: none;
            color: $light-gray;
            background-color: $blue;
            border-radius: 12px;
            cursor: pointer;
        }
    }

</style>