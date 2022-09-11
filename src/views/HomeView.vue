<template>
  <div class="home">
    <div class="logo">
      <router-link to="/">UI KIT PRO</router-link>
    </div>
    <Nav />
  </div>
</template>

<script>
// @ is an alias to /src

import Nav from "@/components/Nav.vue";

export default {
  name: "HomeView",
  components: {
    Nav,
  },
};
</script>

<style lang="scss" scoped>
@import "../scss/_mixins.scss";

.home {
  @include allFlex($justify: space-between);

  .logo {
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    a {
      color: white;
      text-decoration: none;
      font-weight: bold;
      font-size: 20px;
    }
  }
}
</style>
