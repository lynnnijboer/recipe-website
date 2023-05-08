<template>
  <footer id="footerModule" class="footer">
    <textBlock
      v-for="(textBlock, index) in textBlocks"
      :key="index"
      :title="textBlock.title"
      :text="textBlock.text"
      :adress="textBlock.adress"
      :adressLink="textBlock.adressLink"
    />
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

<style lang="scss" scoped></style>
