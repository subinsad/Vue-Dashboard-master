<template>
    <LayoutLong title="중장비 점검" class="layout">
        <ProcessBar
            class="ProcessBar"
            label="미점검"
            count="10"
            name="점검완료"
            number="15"
        />
        <div class="layout__wrap">
            <div class="layout__wrap__block">
                <div class="bar" v-for="item in barData">
                    <div class="bar__block">
                        <div class="back">
                            <div
                                class="front"
                                :style="{ height: `${setHeight(item)}%` }"
                            ></div>
                        </div>
                    </div>
                    <span>{{ item.name }}</span>
                </div>
            </div>
        </div>
    </LayoutLong>
</template>

<script>
import LayoutLong from "../Layout/LayoutLong.vue";
import Details from "../components/Button/Details.vue";
import ProcessBar from "../components/chip/ProcessBar.vue";

export default {
    components: { Details, LayoutLong, ProcessBar },

    data() {
        return {
            barData: [
                {
                    total: 100,
                    doing: 20,
                    name: "굴삭기",
                },
                {
                    total: 100,
                    doing: 30,
                    name: "중장비",
                },
                {
                    total: 100,
                    doing: 40,
                    name: "파일항타",
                },
                {
                    total: 100,
                    doing: 50,
                    name: "양중기",
                },
                {
                    total: 100,
                    doing: 60,
                    name: "산업보건",
                },
            ],
        };
    },
    methods: {
        setHeight(item) {
            const res = String((item.doing / item.total) * 100);
            return res;
        },
    },
};
</script>

<style lang="scss" scoped>
@import "../scss/main.scss";

.layout {
    height: 256px;

    &__wrap {
        display: flex;
        flex-direction: column;
        justify-content: space-around;

        margin-top: 20px;

        &__block {
            display: flex;
            justify-content: space-around;

            position: relative;

            @mixin block {
                display: inline-block;

                width: 15px;

                border-radius: 10px;
            }
            .bar {
                display: flex;
                flex-direction: column;

                gap: 12px;

                &__block {
                    height: 125px;

                    .back {
                        @include block;
                        position: relative;

                        height: 100%;

                        background-color: $Color-gray-005;
                    }

                    .front {
                        @include block;
                        display: flex;

                        position: absolute;
                        bottom: 0px;

                        height: 70px;
                        background-color: $Color-blue-050;
                    }
                }
            }
        }
    }
}
</style>
