<template>
    <LayoutLong title="부적합" class="layout">
        <ProcessBar
            class="ProcessBar"
            label="미조치"
            count="5"
            name="조치완료"
            number="10"
        />
        <div class="layout__wrap">
            <BarChart class="layout__chart" />

            <div class="layout__wrap__total">
                <span> 45명</span>
            </div>
            <ul class="list">
                <li class="list__text-box">
                    <span class="list__text-box__box-blue"></span>
                    <span class="list__text-box__text">{{ name }}</span>
                    <span>{{ number }}명</span>
                </li>

                <li class="list__text-box">
                    <span class="list__text-box__box-blue02"></span>
                    <span class="list__text-box__text">{{ west }}</span>
                    <span>{{ numberWest }}명</span>
                </li>

                <li class="list__text-box">
                    <span class="list__text-box__box-gray"></span>
                    <span class="list__text-box__text">{{ other }}</span>
                    <span>{{ numberOther }}명</span>
                </li>
            </ul>
        </div>
    </LayoutLong>
</template>

<script>
import LayoutLong from "../Layout/LayoutLong.vue";
import Details from "../components/Button/Details.vue";
import BarChart from "../components/BarChart.vue";
import ProcessBar from "../components/chip/ProcessBar.vue";

export default {
    components: { Details, BarChart, LayoutLong, ProcessBar },

    data() {
        return {
            name: "A구역",
            number: "10",
            west: "B구역",
            numberWest: "20",
            other: "C구역",
            numberOther: "15",
        };
    },
};
</script>

<style lang="scss" scoped>
@import "../scss/Font.scss";
.layout {
    height: 256px;
    position: relative;

    &__chart {
        display: flex;

        width: 140px;
        height: 140px;

        margin-top: 24px;
        margin-left: 24px;
    }

    &__wrap {
        display: flex;
        justify-content: space-between;

        margin-top: 20px;

        &__total {
            position: absolute;

            top: 188px;
            left: 86px;

            font-size: 30px;
            font-weight: $font-weight-500;
        }

        .list {
            display: flex;
            flex-direction: column;
            justify-content: space-around;
            text-align: left;

            padding: 0;
            margin-right: 20px;

            width: 40%;

            font-weight: 600;

            &__text-box {
                display: flex;
                flex-direction: row;
                align-items: center;
                justify-content: space-between;

                @mixin box {
                    display: block;
                    content: "";

                    width: 15px;
                    height: 15px;
                    margin-right: 8px;

                    border-radius: 4px;
                }

                &__box-blue {
                    @include box;
                    background-color: #1a4568;
                }

                &__box-blue02 {
                    @include box;
                    background-color: #90afc4;
                }

                &__box-gray {
                    @include box;
                    background-color: #d9d9d9;
                }

                &__text {
                    margin-right: 8px;
                }
            }
        }
    }
}
</style>
