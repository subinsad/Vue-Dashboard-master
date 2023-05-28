<template>
  <div class="wrap">
    <Header />
    <div class="wrap__top">
      <Day />
      <Company />
      <Info />
    </div>

    <div class="wrap__bottom">
      <WorkPermit />
    </div>
  </div>
</template>

<script>
import Day from "./components/Day.vue";
import Info from "./components/info.vue";
import Company from "./components/company.vue";
import WorkPermit from "./components/WorkPermit.vue";
import Header from "./components/Header/Header.vue";
export default {
  components: {
    Day,
    Info,
    Company,
    WorkPermit,
    Header,
  },
  data() {
    return {};
  },
};
</script>

<style lang="scss" scoped>
.wrap {
  display: grid;
  justify-content: center;

  gap: 20px;
  &__top {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 0 20px;
  }
}
</style>
