<template>
    <div class="modules">
      <modules :modules="modules"/>
    </div>
</template>

<script>

export default {
  name: 'IndexPage',
  data() {
    return {
      data() {
        return {
          currentPage: {},
        };
      },
      async fetch() {
        const { items } = await this.$contentful.getEntries({
          content_type: 'homepage',
          include: 4,
        });

        [this.currentPage] = items;
      },
      modules: [
        {
          type: 'hero',
          title: 'Find here low calorie recipes',
          text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
          buttonColor: 'alpha',
          secondButtonColor: '',
          buttonText: 'All recipes',
          secondButtonText: 'Contact me',
        },
        {
          type: 'recipeBlock',
          recipeBlocks: [
            {
              title: 'Recept naam',
              text: 'Marketing content creation for brands & individuals. Providing graphic design.',
              time: '30 min',
              kcal: '260kcal',
              img: 'https://images.pexels.com/photos/699953/pexels-photo-699953.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2'
            },
            {
              title: 'Recept naam',
              text: 'Marketing content creation for brands & individuals. Providing graphic design.',
              time: '25 min',
              kcal: '340kcal',
              img: 'https://images.pexels.com/photos/376464/pexels-photo-376464.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2'
            },
            {
              title: 'Recept naam',
              text: 'Marketing content creation for brands & individuals. Providing graphic design.',
              time: '40 min',
              kcal: '630kcal',
              img: 'https://images.pexels.com/photos/2097090/pexels-photo-2097090.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2'
            },
            {
              title: 'Recept naam',
              text: 'Marketing content creation for brands & individuals. Providing graphic design.',
              time: '25 min',
              kcal: '520kcal',
              img: 'https://images.pexels.com/photos/2116094/pexels-photo-2116094.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2'
            },
            {
              title: 'Recept naam',
              text: 'Marketing content creation for brands & individuals. Providing graphic design.',
              time: '30 min',
              kcal: '260kcal',
              img: 'https://images.pexels.com/photos/699953/pexels-photo-699953.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2'
            },
            {
              title: 'Recept naam',
              text: 'Marketing content creation for brands & individuals. Providing graphic design.',
              time: '25 min',
              kcal: '340kcal',
              img: 'https://images.pexels.com/photos/376464/pexels-photo-376464.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2'
            },
            {
              title: 'Recept naam',
              text: 'Marketing content creation for brands & individuals. Providing graphic design.',
              time: '40 min',
              kcal: '630kcal',
              img: 'https://images.pexels.com/photos/2097090/pexels-photo-2097090.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2'
            },
            {
              title: 'Recept naam',
              text: 'Marketing content creation for brands & individuals. Providing graphic design.',
              time: '25 min',
              kcal: '520kcal',
              img: 'https://images.pexels.com/photos/2116094/pexels-photo-2116094.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2'
            },
          ]
        },
        {
          type: 'textBlock',
          backgroundDark: false,
          textBlocks: [
            {
              title: 'How to make it?',
              text: 'CO-DA Studios is a digital media content production company specializing in marketing content creation for brands & individuals. Providing graphic design, video production, photography, and animation that seek to inspire your brand’s clientele.',
              listItems: [
                {
                  step: 'Step 1',
                  instructions: 'CO-DA Studios is a digital media content production company specializing in marketing content creation for brands & individuals.',
                  img: 'https://images.pexels.com/photos/2116094/pexels-photo-2116094.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2'
                },
                {
                  step: 'Step 2',
                  instructions: 'CO-DA Studios is a digital media content production company specializing in marketing content creation for brands & individuals.',
                  img: 'https://images.pexels.com/photos/5894552/pexels-photo-5894552.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2'
                },
                {
                  step: 'Step 3',
                  instructions: 'CO-DA Studios is a digital media content production company specializing in marketing content creation for brands & individuals.',
                  img: 'https://images.pexels.com/photos/4781414/pexels-photo-4781414.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2'
                },
              ]
            },
          ]
        },
        // {
        //   type: 'cases',
        //   title: 'My projects',
        //   caseBlocks: [
        //     {
        //       title: 'Hallo',
        //       img: "https://images.pexels.com/photos/3007355/pexels-photo-3007355.jpeg?auto=compress&cs=tinysrgb&w=800",
        //       icon: "arrow-right"
        //     },
        //     {
        //       title: 'Project',
        //       img: "https://images.pexels.com/photos/6294444/pexels-photo-6294444.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2",
        //       icon: "arrow-right"
        //     },
        //     {
        //       title: 'Lynn',
        //       img: "https://images.pexels.com/photos/2047905/pexels-photo-2047905.jpeg?auto=compress&cs=tinysrgb&w=800",
        //       icon: "arrow-right"
        //     }
        //   ]
        // },
        // {
        //   type: 'textBlock',
        //   backgroundDark: true,
        //   textBlocks: [
        //     {
        //       title: 'Nuxt/Vue.js',
        //       text: 'CO-DA Studios is a digital media content production company specializing in marketing content creation for brands & individuals. Providing graphic design, video production, photography, and animation that seek to inspire your brand’s clientele.',
        //       buttonColor: 'alpha',
        //       buttonText: '',
        //     },
        //     {
        //       title: 'Nuxt.js',
        //       text: 'CO-DA Studios is a digital media content production company specializing in marketing content creation for brands & individuals. Providing graphic design, video production, photography, and animation that seek to inspire your brand’s clientele.',
        //       buttonColor: 'alpha',
        //       buttonText: '',
        //     },
        //   ]
        // },
        // {
        //   type: 'imageTextBlock',
        //   buttonColor: 'alpha',
        //   buttonText: 'See more',
        //   title: 'How i started',
        //   img: "https://images.pexels.com/photos/2449600/pexels-photo-2449600.png?auto=compress&cs=tinysrgb&w=800",
        //   text: 'CO-DA Studios is a digital media content production company specializing in marketing content creation for brands & individuals. Providing graphic design, video production, photography, and animation that seek to inspire your brand’s clientele.',
        // },
        // {
        //   type: 'textSlider',
        //   textSlider: [
        //     {
        //       word: 'designer'
        //     },
        //     {
        //       word: 'media'
        //     },
        //     {
        //       word: 'agency'
        //     },
        //     {
        //       word: 'designer'
        //     },
        //     {
        //       word: 'media'
        //     },
        //   ]
        // },
      ]
    }
  }
}
</script>
