<template>
  <LayoutLong title="업체별 출역현황" class="layout">
    <BarChart class="layout__chart" />
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
.layout {
  height: 230px;

  &__chart {
    width: 250px;
    height: 250px;
  }
}
</style>
