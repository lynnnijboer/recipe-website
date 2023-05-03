<template>
    <div class="container">
        <nuxtLink to="/" class="h5 text-color-dark">Back to home</nuxtLink>
        <modulesTextBlockModule
            v-if="recipeBlock"
            :title="recipeBlock.fields.title"
            :ingredients="recipeBlock.fields.ingredients"
            :listItems="recipeBlock.fields.listItems"
        />
    </div>
</template>
<script>

export default {
    name: 'recipeBlock',
    data() {
        return {
            recipeBlock: null,
        };
    },
    async fetch() {
        const recipeBlock = await this.$contentful.getEntries({
            content_type: "recipeBlock",
            "fields.slug": this.$route.params.slug,
            include: 4,
        });
        if (recipeBlock.items.length === 0) {
            this.$nuxt.error({ statusCode: 404, message: "Page not found" });
        }
        else {
            [this.recipeBlock] = recipeBlock.items;
        }
    },
};
</script>