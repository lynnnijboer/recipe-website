<template>
  <div class="textBlock">
    <h4>{{ title }}</h4>
    <p>{{ text }}</p>
    <a :href="adressLink">{{ adress }}</a>
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
    adress: {
      type: String,
    },
    adressLink: {
      type: String,
    },
  },
};
</script>

<style></style>
