
<template>
    <div id="recipeBlockModule" class="recipeBlockModule">
      <div class="container">
        <h3 class="recipeBlockModule__title">{{ title }}</h3>
        <button class="recipeBlockModule__button" @click="sortItems('title')">alphabet</button>
        <button class="recipeBlockModule__button" @click="sortItems('kcal')">kcal</button>
        <button class="recipeBlockModule__button" @click="sortItems('time')">time</button>
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
  name: 'recipeBlockModule',
  props: {
    recipeBlocks: {
      type: Array,
      required: true
    },
    title: {
      type: String,
    }
  },
  data(){
    return{
      sortValue: 'title'
    }
  },
  methods: {
    sortItems(value){
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
  mounted(){
    this.recipeBlocks.sort(this.compareAll)
  }
}

</script>

<style lang="scss" scoped>
.recipeBlockModule {
  padding: {
    top: rem(100px);
    bottom: rem(100px);
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
