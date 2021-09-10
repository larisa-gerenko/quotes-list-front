<template>
  <div>

      <v-card
          :loading="loading"
          class="mx-auto my-12"
          max-width="90%"
      >

        <v-card-title>Фридрих Ницше</v-card-title>

        <v-card-text>
          <div>«Культура – это лишь тоненькая яблочная кожура над раскаленным хаосом».</div>
        </v-card-text>

        <v-divider class="mx-4"></v-divider>
        <v-card-text>
          <v-chip-group
              v-model="selection"
              active-class="deep-purple accent-4 white--text"
              column
              multiple
          >
              <v-chip>
                Культура
              </v-chip>
              <v-chip>
                Философия
              </v-chip>
          </v-chip-group>
        </v-card-text>

      </v-card>

  </div>
</template>

<script>
  export default {
    name: 'HelloWorld',

    data: () => ({
      ecosystem: [
        {
          text: 'vuetify-loader',
          href: 'https://github.com/vuetifyjs/vuetify-loader',
        },
        {
          text: 'github',
          href: 'https://github.com/vuetifyjs/vuetify',
        },
        {
          text: 'awesome-vuetify',
          href: 'https://github.com/vuetifyjs/awesome-vuetify',
        },
      ],
      importantLinks: [
        {
          text: 'Documentation',
          href: 'https://vuetifyjs.com',
        },
        {
          text: 'Chat',
          href: 'https://community.vuetifyjs.com',
        },
        {
          text: 'Made with Vuetify',
          href: 'https://madewithvuejs.com/vuetify',
        },
        {
          text: 'Twitter',
          href: 'https://twitter.com/vuetifyjs',
        },
        {
          text: 'Articles',
          href: 'https://medium.com/vuetify',
        },
      ],
      whatsNext: [
        {
          text: 'Explore components',
          href: 'https://vuetifyjs.com/components/api-explorer',
        },
        {
          text: 'Select a layout',
          href: 'https://vuetifyjs.com/getting-started/pre-made-layouts',
        },
        {
          text: 'Frequently Asked Questions',
          href: 'https://vuetifyjs.com/getting-started/frequently-asked-questions',
        },
      ],
    }),
  }
</script>
