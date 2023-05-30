<template>
  <div class="wrap">
    <div class="wrap__header">
      <Header />
    </div>

    <div class="wrap__dashboard">
      <div class="wrap__dashboard__top">
        <Day />
        <Company /><Company />
        <Info />
      </div>

      <div class="wrap__dashboard__bottom">
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
  },
  data() {
    return {};
  },
};
</script>

<style lang="scss" scoped>
.wrap {
  display: flex;
  justify-content: center;
  flex-direction: column;

  gap: 20px;
  &__dashboard {
    display: flex;
    flex-direction: column;

    gap: 20px;

    &__top,
    &__bottom {
      display: flex;
      justify-content: center;
      gap: 20px;
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
