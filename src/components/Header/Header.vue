<template>
  <div>
    <div class="nav">
      <h1 class="nav__logo"><img src="../../image/logo.png" /></h1>
      <div
        class="nav__item"
        v-for="(item, index) in links"
        :key="item.id"
        :to="`${item.page}`"
        @mouseover="mouseover(item, index)"
      >
        {{ item.text }}
      </div>
    </div>

    <div
      class="nav__subMenu"
      :class="{ active: isActive }"
      @mouseleave="moverleave"
    >
      <div class="nav__subMenu__text-box">
        <div class="text" v-for="item in dropDown" :key="item">
          {{ item.name }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Navigation",
  data() {
    return {
      isActive: false,
      links: [
        {
          id: 0,
          text: "현장관리",
          page: "/",
        },
        {
          id: 1,
          text: "인력/차량",
          page: "/",
        },
        {
          id: 2,
          text: "작업관리",
          page: "/",
        },
        {
          id: 3,
          text: "중장비",
          page: "/",
        },
        {
          id: 4,
          text: "부적합",
          page: "/",
        },
        {
          id: 5,
          text: "게시판",
          page: "/",
        },
        {
          id: 6,
          text: "설정/관리",
          page: "/",
        },
      ],

      dropDown: [],
      subMenu01: [
        {
          name: "공사개요",
        },
        {
          name: "업체관리",
        },
      ],
      subMenu02: [],
      subMenu03: [],
      subMenu04: [],
      subMenu05: [],
      subMenu06: [],
      subMenu07: [],

      // 리펙토링
      subMenu: [
        [
          {
            name: "공사개요",
          },
          {
            name: "업체관리",
          },
        ],
        [
          {
            name: "근로자관리",
          },
          {
            name: "관리자관리",
          },
        ],

        [
          {
            name: "안전교육",
          },
          {
            name: "안전회의록",
          },
        ],

        [
          {
            name: "MSDS",
          },
          {
            name: "위험성평가서",
          },
          {
            name: "협력사위험성평가",
          },
          {
            name: "위험성평가점검",
          },
          {
            name: "작업허가서",
          },
          {
            name: "TBM일지",
          },
        ],

        [
          {
            name: "안전점검부적합",
          },
        ],

        [
          {
            name: "SOS요청이력",
          },
          {
            name: "작업중지요청이력",
          },
        ],
        [
          {
            name: "위험성평가설정",
          },
          {
            name: "현장세부정보설정",
          },
        ],
      ],
    };
  },

  methods: {
    mouseover(item, index) {
      // 서브헤더 display가 none인 상태에서 => block, flex ... 등
      this.isActive = true;

      // 1차원적인 생각
      // if (item.id === 0) this.dropDown = this.subMenu01;
      // if (item.id === 1) this.dropDown = this.subMenu02;
      // if (item.id === 2) this.dropDown = this.subMenu03;
      // if (item.id === 3) this.dropDown = this.subMenu04;
      // if (item.id === 4) this.dropDown = this.subMenu05;
      // if (item.id === 5) this.dropDown = this.subMenu06;
      // if (item.id === 6) this.dropDown = this.subMenu07;

      // 위 코드 리펙토링
      if (item.id === index) this.dropDown = this.subMenu[index];
    },
    moverleave() {
      this.isActive = false;
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../../scss/Font.scss";
@import "../../scss/color.scss";
.nav {
  display: flex;
  align-items: center;
  justify-content: center;

  height: 75px;

  color: $Color-gray-004;
  background-color: #fff;
  font-size: 20px;
  font-weight: $font-weight-700;

  &__item {
    display: flex;
    justify-content: center;
    align-items: center;

    width: 5%;
    height: 100%;
    margin: 0 3%;
  }

  &__item:hover .subMenu {
    cursor: pointer;
    display: block;
  }

  &__logo {
    margin-top: 43px;
  }

  &__subMenu {
    display: none;
    justify-content: center;
    align-items: center;
    position: absolute;
    z-index: 1;

    width: 100%;
    height: 90px;

    background-color: #fff;
    border-top: 1px solid $Color-gray-005;
    opacity: 95%;

    &__text-box {
      display: flex;
      align-items: center;
      justify-content: flex-start;

      height: 100%;
      width: 75%;
      margin-left: 20%;

      font-size: 19px;
      font-weight: $font-weight-500;

      .text {
        display: flex;
        align-items: center;
        justify-content: center;

        margin-right: 3%;
        height: 100%;

        color: $Color-gray-004;
      }

      .text:hover {
        color: $Color-blue-100;
        cursor: pointer;
      }
    }
  }

  &__subMenu.active {
    display: block;
  }
}

.nav__item:hover .nav__subMenu {
  cursor: pointer;
  display: block;
}
</style>
