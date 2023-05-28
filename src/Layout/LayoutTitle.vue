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

  width: 386px;
  height: 238px;
  padding: 16px 32px;

  background-color: #fff;
  border-radius: 10px;
}
</style>
