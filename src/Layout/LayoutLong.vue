<template>
  <div class="Layout">
    <div v-if="title === ''" class="Layout__title">
      {{ title }}
    </div>
    <div v-else class="Layout__title">
      {{ title }}
      <Details />
    </div>

    <slot> </slot>
  </div>
</template>

<script>
import Details from "../components/Button/Details.vue";
export default {
  components: { Details },
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

  width: 410px;
  height: 580px;
  padding: 20px;

  background-color: #fff;
  border-radius: 10px;

  &__title {
    display: flex;
    justify-content: space-between;

    margin-bottom: 16px;

    font-weight: $font-weight-700;
    font-size: 17px;
  }
}
</style>
