<template>
  <Layout>
    <div class="dateBox">
      <div class="dateBox__information">
        <div class="dateBox__information__text">
          <p class="location">구미 천연가스 발전소 현장</p>
          <span class="date">{{ currentTime }}</span>
          <div class="dateBox__information__calender">
            <img src="../image/day.png" alt="" class="icon-day" />
            <b class="day">D-365</b>
          </div>
        </div>

        <div class="dateBox__information__countBox">
          <div class="countText">
            <TextBtn :theme="blue"> 착공일 </TextBtn> <span>2022-12-01</span>
          </div>

          <div class="countText">
            <TextBtn :theme="blue"> 준공일 </TextBtn> <span>2023-12-01</span>
          </div>
        </div>
      </div>

      <div class="dateBox__weather">
        <div class="dateBox__weather__image">
          <img src="../image/sun.png" alt="" />
        </div>

        <div class="dateBox__weather__list">
          <ul class="text">
            <li class="text__wind">
              <span>온도 </span>
              <span> 17 </span>
              <span>&#186; C</span>
            </li>

            <li class="text__wind">
              <span>습도 </span>
              <span> 17 </span>
              <span> %</span>
            </li>

            <li class="text__wind">
              <span>풍속 </span>
              <span> 1.3 </span>
              <span> m/s</span>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </Layout>
</template>

<script>
import Layout from "../Layout/LayoutTitle.vue";
import TextBtn from "../components/chip/Chip.vue";
import dayjs from "dayjs";
import "dayjs/locale/ko";
dayjs.locale("ko");

export default {
  components: { Layout, TextBtn },
  data() {
    return {
      blue: "textblue",
      //현재시간 dayjs
      currentTime: dayjs().format("YYYY년 MM월 DD일 (ddd)"),
    };
  },
};
</script>

<style lang="scss" scoped>
@import "../scss/Color.scss";
@import "../scss/Font.scss";

[theme="textblue"] {
  background-color: $Color-blue-001;
  color: $Color-blue-100;
}

.dateBox {
  width: 100%;

  &__information {
    display: flex;
    flex-direction: row;
    justify-content: space-between;

    border-bottom: 1px solid #d3d3d3;
    padding-bottom: 16px;
    &__text {
      display: flex;
      flex-direction: column;

      gap: 12px;
      .location {
        margin: 0;

        font-weight: $font-weight-700;
        font-size: 17px;
      }

      .date {
        font-size: 16px;
      }

      .day {
        font-size: 31px;
      }
    }

    &__calender {
      display: flex;
      align-items: center;
      justify-content: center;

      .icon-day {
        margin-right: 16px;
      }
    }

    &__countBox {
      display: flex;
      flex-direction: column;

      gap: 12px;
      padding-top: 34px;
      .countText {
        display: flex;
        flex-direction: row;

        gap: 16px;
      }
    }
  }

  &__weather {
    display: flex;
    justify-content: center;
    align-items: center;

    margin-top: 8px;

    &__list {
      .text {
        &__wind span:nth-child(2) {
          margin: 0 16px 0 52px;

          color: #00264b;
          font-weight: $font-weight-500;
        }
        &__wind {
          display: flex;

          color: $Color-gray-002;
        }
      }
    }
  }
}
</style>
