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
            <TextBtn :theme="blue"> 착공일 </TextBtn>
            <span>2022-12-01</span>
          </div>

          <div class="countText">
            <TextBtn :theme="blue"> 준공일 </TextBtn>
            <span>2023-12-01</span>
          </div>
        </div>
      </div>

      <div class="dateBox__weather">
        <div class="dateBox__weather__image">
          <img src="../image/sun.png" alt="" />
        </div>

        <div class="dateBox__weather__list">
          <ul class="text">
            <li class="text__wind" v-for="item in temporaryData" :data="item">
              <span>{{ item.title }} </span>
              <span>{{ Math.round(item.value) }}</span>
              <span v-html="item.text"></span>
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
import axios from "axios";
dayjs.locale("ko");

export default {
  components: { Layout, TextBtn },
  data() {
    return {
      blue: "textblue",
      //현재시간 dayjs
      currentTime: dayjs().format("YYYY년 MM월 DD일 (ddd)"),

      temporaryData: [
        {
          title: "온도",
          value: "",
          text: "&#8451;",
        },
        {
          title: "습도",
          value: "",
          text: "%",
        },
        {
          title: "풍속",
          value: "",
          text: "m/s",
        },
      ],
    };
  },

  created() {
    const API_KEY = "e7878598157a92ae89d1403b94d8653d";
    let lat = 36.5683;
    let lon = 126.9778;

    axios
      .get(
        `https://api.openweathermap.org/data/2.5/onecall?lat=${lat}&lon=${lon}&appid=${API_KEY}&units=metric`
      )
      .then((response) => {
        console.log(response);

        this.temporaryData[0].value = response.data.current.temp;
        this.temporaryData[1].value = response.data.current.humidity;
        this.temporaryData[2].value = response.data.current.wind_speed;
      })
      .catch((error) => {
        console.log(error);
      });
  },

  methods: {},
};
</script>

<style lang="scss" scoped>
@import "../scss/Color.scss";
@import "../scss/Font.scss";

ul {
  padding: 0;
  margin: 0;
}

[theme="textblue"] {
  background-color: $Color-blue-001;
  color: $Color-blue-100;
}

.dateBox {
  width: 100%;

  &__information {
    display: flex;
    flex-direction: row;
    justify-content: center;

    gap: 62px;
    border-bottom: 1px solid #d3d3d3;
    padding-bottom: 12px;
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
    align-items: center;
    justify-content: space-around;

    margin-top: 8px;

    &__list {
      .text {
        line-height: 34px;
        font-size: 17px;
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
