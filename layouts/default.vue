<template>
    <div>
        <navMenu :buttonText="buttonText" :color="color" :listItems="listItems"/>
        <nuxt />
    </div>
</template>

<script>
import navMenu from "~/components/navMenu.vue";

export default {
    components: { navMenu },
    name: 'default',
    data() {
        return {
            buttonText: 'Contact me',
            color: 'alpha',
            listItems: [
                {
                    itemText: 'Home',
                    link: '#recipeBlockModule',
                },
                {
                    itemText: 'All recipes',
                    link: '#recipeBlockModule',
                },
            ]
        }
    }
}
</script>

<style></style>