<template>
  <div id="recipeBlockModule" class="recipeBlockModule">
    <div class="container">
      <h3 class="recipeBlockModule__title">{{ title }}</h3>
      <div class="recipeBlockModule__wrapper">
        <button class="recipeBlockModule__button" @click="sortItems('kcal')">
          kcal
        </button>
        <button class="recipeBlockModule__button" @click="sortItems('time')">
          time
        </button>
      </div>
      <div class="recipeBlockModule__recipeBlocks">
        <recipeBlock
          v-for="(recipeBlock, index) in recipeBlocks"
          :key="index"
          :text="recipeBlock.fields.text"
          :title="recipeBlock.fields.title"
          :time="recipeBlock.fields.time"
          :img="recipeBlock.fields.img.fields.file.url"
          :kcal="recipeBlock.fields.kcal"
          :slug="recipeBlock.fields.slug"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "recipeBlockModule",
  props: {
    recipeBlocks: {
      type: Array,
      required: true,
    },
    title: {
      type: String,
    },
  },
  data() {
    return {
      sortValue: "kcal",
    };
  },
  methods: {
    sortItems(value) {
      this.sortValue = value;
      this.recipeBlocks.sort(this.compareAll);
    },
    compareAll(a, b) {
      let comparison = 0;
      if (a.fields[this.sortValue] > b.fields[this.sortValue]) {
        comparison = 1;
      } else if (a.fields[this.sortValue] < b.fields[this.sortValue]) {
        comparison = -1;
      }
      return comparison;
    },
  },
  mounted() {
    this.recipeBlocks.sort(this.compareAll);
  },
};
</script>

<style lang="scss" scoped>
.recipeBlockModule {
  padding: {
    top: rem(100px);
    bottom: rem(100px);
  }

  &__wrapper {
    margin-bottom: rem(20px);
    display: flex;
    justify-content: center;
    gap: 10px;

    @include media-breakpoint-up(md) {
      justify-content: start;
    }
  }

  &__button {
    padding: 4px 12px;
    min-width: 88px;
    border: none;
    font: inherit;
    color: var(--color-beta);
    border-radius: 4px;
    outline: none;
    text-decoration: none;
    cursor: default;
    font-weight: 400;
    background-color: var(--color-light);
    border: 1px solid gray;

    &:hover {
      background-color: var(--color-delta);
    }

    &:active {
      background: rgb(213, 212, 212);
    }
  }

  &__title {
    display: flex;
    justify-content: center;
    margin-bottom: 40px;
  }

  &__recipeBlocks {
    display: grid;
    grid-template-columns: 1fr;
    gap: 40px;

    @include media-breakpoint-up(lg) {
      grid-template-columns: 1fr 1fr;
    }
  }
}
</style>
