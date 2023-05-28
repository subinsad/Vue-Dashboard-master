<template>
  <div>
    <slot> </slot>
    <Details />
  </div>
</template>

<script>
import Details from "../Button/Details.vue";
export default {
  components: { Details },
  data() {
    return {
      methods: {},
    };
  },
};
</script>

<style lang="scss" scoped></style>
