<template>
  <footer id="footerModule" class="footer text-color-light">
    <div class="container d-flex">
      <textBlock
        class="col-12 col-sm-6 col-md-4"
        v-for="(textBlock, index) in textBlocks"
        :key="index"
        :title="textBlock.title"
        :text="textBlock.text"
        :link="textBlock.link"
        :linkUrl="textBlock.linkUrl"
      />
    </div>
  </footer>
</template>

<script>
import textBlock from "./textBlock.vue";

export default {
  name: "footerModule",
  components: { textBlock },
  props: {
    textBlocks: {
      type: Array,
    },
  },
};
</script>

<style lang="scss" scoped>
.footer {
  background-color: var(--color-beta);

  padding: {
    top: rem(50px);
    bottom: rem(50px);
  }
}
</style>
