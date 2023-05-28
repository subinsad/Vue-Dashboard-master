<template>
    <div class="Layout">
        <div class="Layout__title">
            {{ title }}
        </div>

        <slot> </slot>
    </div>
</template>

<script>
export default {
    props: {
        title: {
            type: String,
        },
    },
};
</script>

<style lang="scss" scoped>
@import "../scss/Font.scss";
.Layout {
    display: flex;
    flex-direction: column;

    width: 386px;
    height: 578px;
    padding: 16px 32px;

    background-color: #fff;
    border-radius: 10px;

    &__title {
        display: flex;
        margin: 16px 8px;
        margin-right: 0;
        font-weight: $font-weight-700;
        font-size: 17px;
    }
}
</style>
