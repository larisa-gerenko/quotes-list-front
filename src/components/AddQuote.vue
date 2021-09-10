<template>
  <div class="add_quote">
    <v-text-field
        v-model="name"
        class="pt-5"
        filled
        color="brown darken-1"
        label="Автор цитаты"
    ></v-text-field>
    <v-container fluid>
      <v-textarea
          v-model="text"
          filled
          color="brown darken-1"
          autocomplete="Цитата"
          label="Цитата"
      ></v-textarea>
    </v-container>


  <div class="tags">
      <v-checkbox
          v-model="checkbox"
          color="brown darken-1"
          :label="`Наука `"
      ></v-checkbox>
      <v-checkbox
          v-model="checkbox"
          color="brown darken-1"
          :label="`Философия`"
      ></v-checkbox>
      <v-checkbox
          v-model="checkbox"
          color="brown darken-1"
          :label="`Любовь`"
      ></v-checkbox>
      <v-checkbox
          v-model="checkbox"
          color="brown darken-1"
          :label="`Животные`"
      ></v-checkbox>
    <v-checkbox
        v-model="checkbox"
        color="brown darken-1"
        :label="`Дети`"
    ></v-checkbox>
    <v-checkbox
        v-model="checkbox"
        color="brown darken-1"
        :label="`Родители`"
    ></v-checkbox>
    <v-checkbox
        v-model="checkbox"
        color="brown darken-1"
        :label="`Природа`"
    ></v-checkbox>
    <v-checkbox
        v-model="checkbox"
        color="brown darken-1"
        :label="`Страна`"
    ></v-checkbox>
    <v-checkbox
        v-model="checkbox"
        color="brown darken-1"
        :label="`Родина`"
    ></v-checkbox>
    <v-checkbox
        v-model="checkbox"
        color="brown darken-1"

        :label="`Праздник`"
    ></v-checkbox>

  </div>
    <v-btn
        color="brown darken-1"
        text
        outlined
        @click="saveQuote"
    >
      Сохранить
    </v-btn>

  </div>
</template>

<script>


  export default {
    name: 'AddQuote',

    data: () => ({
      name: '',
      text: '',
      checkbox: false,
    }),
    methods: {
      saveQuote: function() {
        this.$emit('save', {
          name: this.name,
          text: this.text,}
          )
      }
    }

  }


</script>
<style>
.container.container--fluid {
  padding: 0;
}
.tags {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
}
.theme--light.v-input.v-input--checkbox{
  width: 26%;
}

</style>
