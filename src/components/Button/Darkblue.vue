<template>
  <button class="text-btn">
    <slot> </slot>
  </button>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "src/scss/Font.scss";
.text-btn {
  display: flex;
  justify-content: center;
  align-items: center;

  padding: 8px 16px;

  border-radius: 3px;
  background-color: #00264b;

  color: #fff;
  font-size: 16px;
  font-weight: $font-weight-500;
}
</style>
