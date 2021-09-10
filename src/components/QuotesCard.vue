<template>
  <div class="quotesCard" id="app">

      <v-card
          class="mx-auto my-12"
          max-width="90%"
      >

        <v-card-title>{{ quotesData.name }}</v-card-title>

        <v-card-text>
          <div>{{ quotesData.text}}</div>
        </v-card-text>

        <v-divider class="mx-4"></v-divider>
        <v-card-text>
          <v-chip-group
              active-class="deep-purple accent-4 white--text"
              column
              multiple

          >
              <v-chip close
                      color="#7a7a7a"
                      small
                      outlined v-for="tag in quotesData.tags " :key="tag">
                {{ tag}}
              </v-chip>


          </v-chip-group>
          <div class="date">{{date}}</div>
        </v-card-text>

      </v-card>

  </div>
</template>

<script>
  export default {
    name: "QuotesCard",

    props: {
      quotesData: {
        type: Object,
        default() {
          return {}
        }
      }
    },
    computed: {
      date: function() {
        const date = new Date(Date.parse(this.quotesData.created_at));
        console.log(date)
        return date.toLocaleDateString("en-US");
      }
    }
  }
</script>

<style scoped>


</style>
