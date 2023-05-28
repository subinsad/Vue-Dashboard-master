<template>
  <div class="text-btn">
    <slot> </slot>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "../../scss/Font.scss";
.text-btn {
  display: inline-flex;
  justify-content: center;
  align-items: center;

  padding: 8px 12px;
  height: 10px;

  border-radius: 3px;

  font-size: 14px;
  font-weight: $font-weight-700;
}
</style>
