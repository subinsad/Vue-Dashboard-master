<template>
  <LayoutLong :title="''" class="layout"> </LayoutLong>
</template>

<script>
import LayoutLong from "../Layout/LayoutLong.vue";
export default {
  components: { LayoutLong },
};
</script>

<style lang="scss" scoped>
.layout {
  background-image: url(../image/Map.png);
  background-repeat: no-repeat;
  background-size: cover;

  border: 10px;
  width: 880px;
}
</style>
