<template>
  <nav class="navigation">
    <div class="hamburger" @click="showMenu()">
      <div class="bar1"></div>
      <div class="bar2"></div>
      <div class="bar3"></div>
    </div>
    <ul
      class="nav-items d-flex list-unstyled px-2"
      :class="this.showMobileMenu ? 'active' : ''"
    >
      <li v-for="(item, index) in listItems" :key="index" class="p-3">
        <a
          @click="showMobileMenu = false"
          class="nav-items__item"
          :href="item.link"
        >
          {{ item.itemText }}
        </a>
      </li>
      <uiButton class="nav-button" :buttonText="buttonText" :color="color" />
    </ul>
  </nav>
</template>

<script>
import uiButton from "./uiButton.vue";

export default {
  name: "navMenu",
  components: { uiButton },
  data() {
    return {
      showMobileMenu: false,
    };
  },
  methods: {
    showMenu() {
      this.showMobileMenu = !this.showMobileMenu;
    },
  },
  props: {
    listItems: {
      type: Array,
    },
    buttonText: {
      type: String,
    },
    color: {
      type: String,
      default: "alpha",
    },
  },
};
</script>

<style lang="scss" scoped>
.navigation {
  z-index: 999;
  position: fixed;
  right: 0;
  top: 0;

  .nav-items {
    height: 0;
    width: 0;
    opacity: 0;

    &.active {
      width: 100vw;
      height: 100vh;
      background-color: var(--color-beta);
      overflow: hidden;
      opacity: 1;
      padding-top: 50px;

      @include media-breakpoint-up(md) {
        height: unset;
        width: unset;
        padding-top: unset;
      }
    }

    @include media-breakpoint-up(md) {
      height: auto;
      width: 100%;
      opacity: 1;
    }
  }

  .hamburger {
    padding: 20px;
    z-index: 1000;
    display: inline-block;
    cursor: pointer;
    position: fixed;
    left: 0;
    top: 0;

    .bar1,
    .bar2,
    .bar3 {
      width: 35px;
      height: 5px;
      background-color: #333;
      margin: 6px 0;
      transition: 0.4s;
    }

    @include media-breakpoint-up(md) {
      display: none;
    }
  }

  .nav-items {
    flex-direction: column;
    align-items: center;

    &__item {
      color: var(--color-light);
      &:hover {
        text-decoration: underline;
      }
    }

    @include media-breakpoint-up(md) {
      flex-direction: row;
      justify-content: flex-end;
    }
  }
}
</style>
