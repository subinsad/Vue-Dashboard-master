<template>
    <div class="chip">
        <p class="chip__text">작업중</p>
    </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "../../scss/Font.scss";
.chip {
    display: inline-flex;
    justify-content: center;
    align-items: center;

    font-size: 14px;
    font-weight: $font-weight-700;

    &__text {
        display: flex;
        align-items: center;
        justify-content: center;

        width: 80px;
        height: 30px;
        border-radius: 3px;
        background-color: #f7fff6;
        color: #51881a;
    }
}
</style>
