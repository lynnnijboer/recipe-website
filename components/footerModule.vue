<template>
  <footer id="footerModule" class="footer">
    <textBlock
      v-for="(textBlock, index) in textBlocks"
      :key="index"
      :title="textBlock.fields.title"
      :text="textBlock.fields.text"
      :adress="textBlock.fields.adress"
      :adressLink="textBlock.fields.adressLink"
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
