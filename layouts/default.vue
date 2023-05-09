<template>
  <div>
    <navMenu :buttonText="buttonText" :color="color" :listItems="listItems" />
    <nuxt />
    <footerModule :textBlocks="textBlocks" />
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
      textBlocks: [
        {
          title: "Home",
          text: "At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis.",
          link: "",
          linkUrl: "",
        },
        {
          title: "link",
          text: "",
          link: "Hofstedeweg 220, 7535CZ Enschede",
          linkUrl: "https://goo.gl/maps/KVGxLFwBJ7UpWopc8?coh=178571&entry=tt",
        },
        {
          title: "All recipes",
          text: "",
          link: "See all recipes",
          linkUrl: "#recipeBlockModule",
        },
      ],
    };
  },
};
</script>

<style></style>
