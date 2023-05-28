<template>
  <Layout>
    <div class="profile">
      <div class="profile__text">
        <span class="profile__text__company">[지에스아이엘]</span>
        <span class="profile__text__name">김서부 ㅣ 안전관리자</span>
      </div>

      <div class="profile__logout">
        <TextBtn :theme="Darkblue"> 로그아웃</TextBtn>
      </div>
    </div>

    <div class="count">
      <div class="count__title">
        <span class="count__title__text">결재현황</span>
      </div>
      <div class="count__list">
        <ul class="count__list__box">
          <!-- 컴포넌트화 하지 않았을 경우 -->
          <li
            v-for="(item, index) in approvalList"
            :data="item"
            class="Approval"
          >
            <span class="Approval__text">{{ item.label }}</span>
            <span class="Approval__number"
              >{{ item.count
              }}<span class="Approval__number__case">건 </span></span
            >
          </li>
          <!-- 컴포넌트화 했을 경우 -->
          <!-- <List
            v-for="(item, index) in approvalList"
            :key="index"
            :data="item"
          /> -->
        </ul>
      </div>
    </div>
  </Layout>
</template>

<script>
import Layout from "../Layout/LayoutTitle.vue";
import TextBtn from "../components/Button/Darkblue.vue";

export default {
  props: {
    item: {
      type: Object,
      required: true,
    },
  },
  components: { Layout, TextBtn },
  data() {
    return {
      blue: "textblue",
      // 배열 & 객체
      approvalList: [
        {
          label: "결재대기",
          count: 3,
        },
        {
          label: "결재진행",
          count: 10,
        },
        {
          label: "반려",
          count: 12,
        },
        {
          label: "결재완료",
          count: 20,
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
@import "../scss/Color.scss";
@import "../scss/Font.scss";
.Layout {
  flex-direction: column;
}
.profile {
  display: flex;
  flex-direction: row;

  align-items: center;
  justify-content: space-between;
  margin-bottom: 32px;
  &__text {
    display: flex;
    flex-direction: column;
    align-items: flex-start;

    font-size: 17px;

    &__company {
      margin-bottom: 16px;

      font-weight: $font-weight-700;
    }
  }

  &__logout {
    display: flex;
    align-items: center;
  }
}
.count {
  &__title {
    display: flex;

    padding: 8px 12px;

    background-color: $Color-blue-002;
    font-size: 17px;
    color: $Color-blue-100;
    font-weight: $font-weight-700;
  }
  &__list {
    &__box {
      // display: flex;
      // flex-direction: row;
      display: grid;
      grid-template-columns: repeat(2, 1fr);

      padding: 0 12px;
      gap: 12px 24px;

      .Approval {
        display: flex;
        align-items: center;
        justify-content: space-between;

        border-bottom: 1px solid $Color-gray-003;

        font-weight: $font-weight-500;

        &__text {
          display: flex;
          width: 50%;
        }

        &__number {
          display: flex;
          align-items: center;
          justify-content: flex-end;

          width: 50%;

          color: $Color-blue-050;

          &__case {
            color: #000;
          }
        }
      }
    }
  }
}
</style>
