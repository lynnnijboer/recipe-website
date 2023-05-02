<template>
  <section>
    <div 
      v-for="(module, index) in modules" 
      :key="index">
      <modulesTextBlockModule 
        v-if="module.sys.contentType.sys.id === 'textBlockModule'" 
        :title="module.fields.title"
        :ingredients="module.fields.ingredients"
        :listItems="module.fields.listItems"
      />
      <modulesRecipeBlockModule 
        v-if="module.sys.contentType.sys.id === 'recipeBlockModule'" 
        :recipeBlocks="module.fields.recipeBlocks"
        :title="module.fields.title"
      />
    </div>
  </section>
</template>

<script>

export default {
  name: 'modules',
  props: {
    modules: {
      type: Array,
      required: true
    }
  }
}
</script>
