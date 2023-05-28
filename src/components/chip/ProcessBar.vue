<template>
  <div class="ProcessBar">
    <div v-for="(item, index) in work" :data="item" class="ProcessBar__work">
      <span class="ProcessBar__work__name">
        {{ item.label }}
      </span>

      <span class="ProcessBar__work__number">
        {{ item.count }}
      </span>

      <span class="ProcessBar__work__text"> 건</span>
    </div>

    <span class="ProcessBar__work__bar" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      work: [
        {
          label: "작업중",
          count: "10",
        },

        {
          label: "작업종료",
          count: "10",
        },
      ],
    };
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
