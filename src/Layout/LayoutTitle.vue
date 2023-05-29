<template>
    <div class="Layout">
        <slot> </slot>
    </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.Layout {
    display: flex;
    flex-direction: column;

    width: 410px;
    height: 230px;
    padding: 20px;

    background-color: #fff;
    border-radius: 10px;
}
</style>
