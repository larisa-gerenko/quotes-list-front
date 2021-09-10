<template>

  <div class="home">
    <div class="header">
      <v-dialog
          v-model="dialog"
          width="500"
      >
        <template v-slot:activator="{ on, attrs }">
          <v-btn class="btn_add_quote"
              color="#ffb703"

              v-bind="attrs"
              v-on="on"
          >
            Добавить цитату
          </v-btn>
        </template>

        <v-card>
          <v-card-title class="text-h5 amber lighten-1" >
            Добавить цитату
          </v-card-title>

          <v-card-text>
            <add-quote v-on:save="createQuote" />
          </v-card-text>

          <v-divider></v-divider>


        </v-card>
      </v-dialog>
    </div>
    <quotes-card
        v-for="quote in quotesList"
        :key="quote.id"
        :quotesData="quote"
    />

    <v-pagination

        :length="3"
    ></v-pagination>



  </div>
</template>

<script>
  import QuotesCard from '../components/QuotesCard'
  import AddQuote from '../components/AddQuote'
  import axios from "axios";

  export default {
    name: 'Home',
    components: {
      QuotesCard,
      AddQuote,
    },

    data: () => {
      return {
        dialog: false,
        quotesList: []
      }
    },
    mounted() {
      axios
          .get('http://localhost/quotes')
          .then(response => (this.quotesList = response.data));
    },
    methods: {
      createQuote: function(dataQuote) {
        axios
            .post('http://localhost/add', dataQuote)
            .then(()=>{
              this.dialog=false;
              axios
                  .get('http://localhost/quotes')
                  .then(response => (this.quotesList = response.data));
            });
      }
    }
  }
</script>
<style>
.header {
  width: 90%;
  margin: 20px auto;
}
.btn_add_quote {
  box-shadow: none;
}
</style>
