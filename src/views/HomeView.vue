<template>
  <div class="home">
    <div class="logo">
      <router-link to="/">UI KIT PRO</router-link>
    </div>
    <Nav Class="nav" />
    <div class="before" @click="toggleClass">
      <i class="fa-solid fa-bars"></i>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

import Nav from "@/components/Nav.vue";

export default {
  name: "HomeView",
  setup() {
    //

    function toggleClass() {
      const nav = document.querySelector(".nav");
      nav.classList.add("list");
    }

    return {
      toggleClass,
    };
  },
  components: {
    Nav,
  },
};
</script>

<style lang="scss" scoped>
@import "../scss/_mixins.scss";

.home {
  @include allFlex($justify: space-between);
  width: 100%;
  height: 3em;
  position: relative;
  background-color: rgba(87, 87, 87, 0.511);
  

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

  .before {
    visibility: hidden;
    z-index: auto;
    cursor: pointer;
    height: 100%;
    width: 3em;
    @include allFlex($justify: center);
    transition: 300ms;

    i {
      font-size: 1.4em;
    }
  }

  @media (max-width: 900px) {
    .before {
      visibility: visible;
    }
  }
}
</style>
