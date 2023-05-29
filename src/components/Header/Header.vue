<template>
    <div>
        <div class="nav">
            <h1 class="nav__logo"><img src="../../image/logo.png" /></h1>
            <router-link
                class="nav__item"
                v-for="routes in links"
                v-bind:key="routes.id"
                :to="`${routes.page}`"
                >{{ routes.text }}</router-link
            >
            <!-- <div>
                <p class="nav__item">{{ dropDown }}</p>
            </div> -->
        </div>
    </div>
</template>

<script>
export default {
    name: "Navigation",
    data() {
        return {
            links: [
                {
                    id: 0,
                    text: "현장관리",
                    page: "/",
                },
                {
                    id: 1,
                    text: "인력/차량",
                    page: "/",
                },
                {
                    id: 2,
                    text: "작업관리",
                    page: "/",
                },
                {
                    id: 3,
                    text: "중장비",
                    page: "/",
                },
                {
                    id: 4,
                    text: "부적합",
                    page: "/",
                },
                {
                    id: 5,
                    text: "게시판",
                    page: "/",
                },
                {
                    id: 6,
                    text: "설정/관리",
                    page: "/",
                },
            ],
        };
    },
};
</script>

<style lang="scss" scoped>
@import "../../scss/Font.scss";
.nav {
    display: flex;
    justify-content: space-around;
    align-items: center;

    height: 75px;

    color: gray;
    background-color: #fff;
    font-size: 20px;
    font-weight: $font-weight-700;

    &__item::before {
        content: "";
        display: none;
        position: relative;
        top: -3px;

        margin: 0 auto;

        width: 6px;
        height: 6px;
        background-color: black;
        border-radius: 10px;
    }

    &__item:hover {
        cursor: pointer;

        color: black;
    }

    &__item:hover::before {
        display: block;
    }

    &__logo {
        margin-top: 43px;
    }
}
</style>
