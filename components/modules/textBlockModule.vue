
<template>
  <div class="textBlockModule">
    <div class="container">
        <div class="textBlockModule__textBlock w-100">
            <h3 class="title h4">{{ title }}</h3>
            <li 
              v-for="(ingredient, index) in ingredients" 
              :key="`ingredient-${index}`"
              class="text">
              {{ ingredient }}
            </li>
            <div
              v-for="(item, index) in listItems" 
              :key="`item-${index}`"
              class="listItems">
              <div class="listItems__content">
                <li class="h6 listItems__step">{{ item.fields.step }}</li>
                <p class="listItems__instructions">{{ item.fields.instruction }}</p>
                </div>
                <div 
                  class="listItems__image" 
                  :style="{ '--bg-img': `url('${item.fields.img.fields.file.url}')` }"
                >
              </div>
          </div>
      </div>
    </div>
  </div>
</template>
<script>

export default {
  name: "textBlockModule",
  props: {
    title: {
      type: String,
    },
    ingredients: {
      type: Array,
    },
    listItems: {
      type: Array,
    }
  },
}
</script>

<style lang="scss" scoped>
.textBlockModule {
  padding-top: rem(100px);
  padding-bottom: rem(100px);

  .padding-bg-dark {
    padding-top: rem(50px);
    padding-bottom: rem(50px);
  }

  .grid {
    justify-content: space-between;
    display: grid;
    grid-template-rows: auto;
    grid-template-columns: 1fr;
    gap: 20px;

    @include media-breakpoint-up(md) {
      grid-template-columns: 1fr 1fr;
      gap: 40px;
    }

    @include media-breakpoint-up(lg) {
      grid-template-columns: auto auto auto;
      gap: 40px;
    }
  }

  &__textBlock {

    .listItems {
      margin-top: 40px;
      box-shadow: rgba(0, 0, 0, 0.1) 0px 1px 6px;
      cursor: pointer;
      border-radius: 2rem;
      background-color: var(--color-light);
      display: grid;
      grid-template-rows: 2fr 1.5fr;
      grid-template-columns: 1fr;
      overflow: hidden;

      @include media-breakpoint-up(sm) {
        grid-template-columns: 2fr 1.5fr;
        grid-template-rows: 1fr;
        height: 250px;
      }

      &__image {
        background-image: var(--bg-img);
        background-size: cover;
      }

      &__content {
        padding: 2rem;
      }

      &__step {
        list-style-type: none;
        font-weight: bold;
      }
    }

    .text {
      width: 100%;
      max-width: 600px;
    }
  }
}
</style>
