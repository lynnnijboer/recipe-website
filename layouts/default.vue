<template>
  <div>
    <navMenu :buttonText="buttonText" :color="color" :listItems="listItems" />
    <nuxt />
    <footerModule />
  </div>
</template>

<script>
import navMenu from "~/components/navMenu.vue";
import footerModule from "~/components/footerModule.vue";

export default {
  components: { navMenu, footerModule },
  name: "default",
  data() {
    return {
      buttonText: "Contact me",
      color: "alpha",
      listItems: [
        {
          itemText: "Home",
          link: "",
        },
        {
          itemText: "All recipes",
          link: "#recipeBlockModule",
        },
      ],
    };
  },
};
</script>

<style></style>
