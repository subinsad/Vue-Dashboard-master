<template>
  <LayoutLong title="업체별 출역현황" class="layout">
    <BarChart class="layout__chart" />

    <div class="layout__total">
      <span> 45명</span>
    </div>

    <div>
      <ul>
        <li></li>
      </ul>
    </div>
  </LayoutLong>
</template>

<script>
import LayoutLong from "../Layout/LayoutLong.vue";
import Details from "../components/Button/Details.vue";
import BarChart from "../components/BarChart.vue";
export default {
  components: { Details, BarChart, LayoutLong },

  data() {
    return {};
  },
};
</script>

<style lang="scss" scoped>
@import "../scss/Font.scss";
.layout {
  height: 230px;
  position: relative;

  &__chart {
    display: flex;

    width: 140px;
    height: 140px;

    margin-top: 24px;
    margin-left: 24px;
  }

  &__total {
    position: absolute;

    top: 133px;
    left: 86px;

    font-size: 30px;
    font-weight: $font-weight-500;
  }
}
</style>
