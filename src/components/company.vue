<template>
  <LayoutLong title="업체별 출역현황" class="layout">
    <div class="layout__wrap">
      <BarChart class="layout__chart" />

      <div class="layout__wrap__total">
        <span> 45명</span>
      </div>
      <ul class="list">
        <li class="list__text-box">
          <span class="list__text-box__box-blue"></span>
          <span class="list__text-box__text">{{ name }}</span>
          <span>{{ number }}명</span>
        </li>

        <li class="list__text-box">
          <span class="list__text-box__box-blue02"></span>
          <span class="list__text-box__text">{{ west }}</span>
          <span>{{ numberWest }}명</span>
        </li>

        <li class="list__text-box">
          <span class="list__text-box__box-gray"></span>
          <span class="list__text-box__text">{{ other }}</span>
          <span>{{ numberOther }}명</span>
        </li>
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
    return {
      name: "지에스아이엘",
      number: "10",
      west: "서부발전",
      numberWest: "20",
      other: "그 외",
      numberOther: "15",
    };
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

    margin-top: 24px;
    margin-left: 24px;
  }

  &__wrap {
    display: flex;
    justify-content: space-between;

    &__total {
      position: absolute;

      top: 135px;
      left: 86px;

      font-size: 30px;
      font-weight: $font-weight-500;
    }

    .list {
      display: flex;
      flex-direction: column;
      justify-content: space-around;
      text-align: left;

      padding: 0;
      margin-right: 20px;

      width: 40%;

      font-weight: 600;

      &__text-box {
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: space-between;

        @mixin box {
          display: block;
          content: "";

          width: 15px;
          height: 15px;
          margin-right: 8px;

          border-radius: 4px;
        }

        &__box-blue {
          @include box;
          background-color: #1a4568;
        }

        &__box-blue02 {
          @include box;
          background-color: #90afc4;
        }

        &__box-gray {
          @include box;
          background-color: #d9d9d9;
        }

        &__text {
          margin-right: 8px;
        }
      }
    }
  }
}
</style>
