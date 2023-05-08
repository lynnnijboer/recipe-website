<template>
  <nuxt-link
    :to="`#${link}`"
    :class="[
      color && variant === 'filled'
        ? `ui-button bg-color-${color} py-1 px-3`
        : '',
      color === 'transparant' ? 'btn-transparant' : '',
    ]"
  >
    {{ buttonText }}
  </nuxt-link>
</template>

<script>
export default {
  name: "uiButton",
  props: {
    buttonText: {
      type: String,
      default: "portfolio",
    },
    variant: {
      type: String,
      default: "filled",
    },
    color: {
      type: String,
      default: "alpha",
    },
    link: {
      type: String,
    },
  },
};
</script>

<style lang="scss" scoped>
.ui-button {
  color: var(--color-light);
  border: unset;
  width: fit-content;

  &:hover {
    border: 0.5px solid white;
  }
}

.btn-transparant {
  background-color: transparent;

  &:hover {
    border: none;
    text-decoration: underline;
  }
}
</style>
