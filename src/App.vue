<template>
  <div class="wrap">
    <div class="wrap__header">
      <Header />
    </div>

    <div class="wrap__dashboard">
      <div class="wrap__dashboard__top">
        <Day />
        <Company /><place />
        <Info />
      </div>

      <div class="wrap__dashboard__bottom">
        <div class="chart">
          <check />
          <unsuitable />
        </div>

        <Map />
        <WorkPermit />
      </div>
    </div>
    <div class="wrap__footer">
      <Footer />
    </div>
  </div>
</template>

<script>
import Day from "./components/Day.vue";
import Info from "./components/info.vue";
import Company from "./components/company.vue";
import WorkPermit from "./components/WorkPermit.vue";
import Map from "./components/Map.vue";
import place from "./components/place.vue";
import unsuitable from "./components/unsuitable.vue";
import check from "./components/check.vue";

import Header from "./components/Header/Header.vue";
import Footer from "./components/Footer.vue";
export default {
  components: {
    Day,
    Info,
    Company,
    WorkPermit,
    Map,
    Header,
    Footer,
    place,
    unsuitable,
    check,
  },
  data() {
    return {};
  },
};
</script>

<style lang="scss" scoped>
.wrap {
  display: flex;
  flex-direction: column;
  justify-content: space-between;

  gap: 20px;

  height: 100vh;

  &__dashboard {
    display: flex;
    flex-direction: column;

    gap: 20px;

    &__top,
    &__bottom {
      display: flex;
      justify-content: center;
      gap: 20px;

      .chart {
        display: flex;
        flex-direction: column;
        gap: 20px;
      }
    }
  }

  &__footer {
    display: flex;
    text-align: right;
    justify-content: flex-end;
    width: calc(100% - 36px);
  }
}
</style>
