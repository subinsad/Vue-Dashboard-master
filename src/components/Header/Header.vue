<template>
  <div>
    <h1><img src="../../image/logo.png" /></h1>

    <div class="nav">
      <router-link
        class="item"
        v-for="routes in links"
        v-bind:key="routes.id"
        :to="`${routes.page}`"
        >{{ routes.text }}</router-link
      >
      <div>
        <p class="item">{{ dropDown }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Navigation",
  data() {
    return {
      links: [
        {
          id: 0,
          text: "현장관리",
          page: "/",
        },
        {
          id: 1,
          text: "현장관리",
          page: "/",
        },
      ],
      dropDown: "",
    };
  },
};
</script>

<style lang="scss" scoped>
.nav {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;

  position: absolute;
  top: 35px;
  right: 164px;
  width: 1300px;

  color: white;
}
</style>
