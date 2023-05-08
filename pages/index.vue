<template>
  <div v-if="currentPage && currentPage.fields" class="index">
    <modulesHeroModule
      :title="currentPage.fields.title"
      :text="currentPage.fields.text"
      :buttonColor="currentPage.fields.buttonColor"
      :buttonText="currentPage.fields.buttonText"
      :secondButtonColor="currentPage.fields.secondButtonColor"
      :secondButtonText="currentPage.fields.secondButtonText"
      :link="currentPage.fields.link"
      :secondLink="currentPage.fields.secondLink"
    />
    <div class="modules">
      <modules :modules="currentPage.fields.modules" />
    </div>
  </div>
</template>

<script>
export default {
  name: "IndexPage",
  data() {
    return {
      currentPage: {},
    };
  },

  async fetch() {
    const { items } = await this.$contentful.getEntries({
      content_type: "homepage",
      include: 5,
    });

    [this.currentPage] = items;
  },
};
</script>
