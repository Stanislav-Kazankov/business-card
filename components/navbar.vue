<template>
    <ul class="navbar">
        <li class="navbar__item"
            v-for="(item, index) of itemData"
            :key="index">
            <nuxt-link
                class="navbar__link"
                :to="item.url"
                active-class="navbar__link--active"
                exact
                no-prefetch
            >
                {{item.caption}}
            </nuxt-link>
        </li>
    </ul>
</template>

<script>
    export default {
        data() {
            return {
                itemData: [
                    {
                        url: '/',
                        caption: 'Главная',
                    },
                    {
                        url: '/about',
                        caption: 'Обо мне',
                    },
                    {
                        url: '/contacts',
                        caption: 'Контакты',
                    },
                ],
            }
        },
    }
</script>

<style lang="scss" scoped>
    @import "@/assets/sass/mixins.scss";

    .navbar {
        display: flex;
        flex-wrap: wrap;
        padding-left: 0;
        padding-top: 30px;
        padding-bottom: 26px;

        list-style: none;

        margin-right: -60px;

        &__item {
            margin-right: 60px;
            margin-bottom: 10px;
        }

        &__link {
            border-top-left-radius: 15px;
            border-top-right-radius: 15px;

            &--active {
                @include make-gradient(
                    #ffffff00,
                    #c4ec35dc,
                    100%
                );
            }
        }
    }
</style>