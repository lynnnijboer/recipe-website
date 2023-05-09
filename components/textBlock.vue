<template>
  <div class="textBlock">
    <h4 v-if="title">{{ title }}</h4>
    <p v-if="title && text">{{ text }}</p>
    <a class="textBlock__link" v-if="link" :href="linkUrl">
      {{ link }}
    </a>
  </div>
</template>

<script>
export default {
  name: "textBlock",
  props: {
    title: {
      type: String,
    },
    text: {
      type: String,
    },
    link: {
      type: String,
    },
    linkUrl: {
      type: String,
    },
  },
};
</script>

<style lang="scss">
.textBlock {
  &__link {
    max-width: 200px;
    cursor: pointer;

    &:hover {
      border: none;
      text-decoration: underline;
    }
  }
}
</style>
