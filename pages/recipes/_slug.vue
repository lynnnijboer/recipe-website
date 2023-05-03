<template>
    <div class="container">
        <nuxtLink to="/" class="h5 text-color-dark">Back to home</nuxtLink>
        <div v-if="recipeBlock">
            <modulesTextBlockModule/>
        </div>
    </div>
</template>
<script>

export default {
    transition: 'recipePage',
    data() {
        return {
            recipeBlock: null,
        };
    },
    async fetch() {
        const recipeBlock = await this.$contentful.getEntries({
            content_type: "recipePage",
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