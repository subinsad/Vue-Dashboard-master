<template>
    <div class="ProcessBar">
        <div class="ProcessBar__work">
            <span class="ProcessBar__work__name">
                {{ label }}
            </span>
            <span class="ProcessBar__work__number">
                {{ count }}
                <span class="ProcessBar__work__text"> 건</span>
            </span>
        </div>

        <div class="ProcessBar__work">
            <span class="ProcessBar__work__name">
                {{ name }}
            </span>

            <span class="ProcessBar__work__number">
                {{ number }}

                <span class="ProcessBar__work__text"> 건</span>
            </span>
        </div>

        <span class="ProcessBar__work__bar" />
    </div>
</template>

<script>
export default {
    props: {
        label: {
            type: String,
        },

        count: {
            type: String,
        },

        name: {
            type: String,
        },

        number: {
            type: String,
        },
    },

    data() {
        return {};
    },
};
</script>

<style lang="scss" scoped>
@import "../../scss/Color.scss";
@import "../../scss/Font.scss";
.ProcessBar {
    display: flex;
    justify-content: space-around;
    align-items: center;
    position: relative;

    height: 40px;

    border: 1px solid $Color-gray-004;
    border-radius: 6px;
    font-weight: $font-weight-500;

    &__work {
        &__name {
            margin-right: 70px;
        }

        &__bar {
            display: inline;
            position: absolute;
            content: "";

            height: 16px;
            width: 2px;
            left: 184px;
            background-color: $Color-gray-004;
        }

        &__number {
            color: $Color-blue-050;
        }
    }
}
</style>
