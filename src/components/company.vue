<template>
  <Layout>
    <div>
      <p>업체별 출역현황</p>
      <!-- <Details /> -->
    </div>

    <BarChart />
  </Layout>
</template>

<script>
import Layout from "../Layout/LayoutTitle.vue";
import Details from "../components/Button/Details.vue";
import BarChart from "../components/BarChart.vue";
export default {
  components: { Layout, Details, BarChart },

  data() {
    return {};
  },
};
</script>

<style lang="scss" scoped></style>
