<template>
    <v-app>
      <v-main>
        <v-card-title>
          <p class="font-weight-medium mt-5">Занимаемые должности</p>
          <v-spacer></v-spacer>
          <v-text-field
            v-model="search"
            append-icon="mdi-magnify"
            label="Поиск по сотруднику"
            single-line
            hide-details
          ></v-text-field>
        </v-card-title>
  
        <v-card-title class="d-flex justify-end mb-6">
          <v-checkbox
            class="mb-5 pr-5"
            v-model="ex4"
            label="Показывать уволенных"
            color="green darken-1"
            value="green darken-1"
            hide-details
          ></v-checkbox>
          <v-btn
            class="mr-5"
            color="green lighten-3"
            elevation="2"
          >принять на должность</v-btn>
          <v-btn
            color="green lighten-3"
            elevation="2"
            disabled
          >снять с должности</v-btn>
        </v-card-title>
      
        <div>
          <v-data-table
            :headers="headers"
            :items="desserts"
            :single-select="singleSelect"
            :search="search"
            item-key="name"
            show-select
            class="elevation-1"
          >
          <template v-slot:[`item.glutenfree`]="{ item }">
            <v-simple-checkbox
              v-model="item.glutenfree"
              color="green darken-1"
            ></v-simple-checkbox>
          </template>
          </v-data-table>
        </div>
      </v-main>
    </v-app>
  </template>

<script>
export default {
  data () {
    return {
      search: '',
      desserts: [
        {
          name: 'Frozen Yogurt',
          calories: 159,
          fat: 6.0,
          carbs: 24,
          protein: 4.0,
          iron: '1%',
          glutenfree: true,
        },
        {
          name: 'Ice cream sandwich',
          calories: 237,
          fat: 9.0,
          carbs: 37,
          protein: 4.3,
          iron: '1%',
          glutenfree: false,
        },
        {
          name: 'Eclair',
          calories: 262,
          fat: 16.0,
          carbs: 23,
          protein: 6.0,
          iron: '7%',
          glutenfree: false,
        },
        {
          name: 'Jelly bean',
          calories: 375,
          fat: 0.0,
          carbs: 94,
          protein: 0.0,
          iron: '0%',
          glutenfree: true,
        },
        {
          name: 'Lollipop',
          calories: 392,
          fat: 0.2,
          carbs: 98,
          protein: 0,
          iron: '2%',
          glutenfree: true,
        },
        {
          name: 'KitKat',
          calories: 518,
          fat: 26.0,
          carbs: 65,
          protein: 7,
          iron: '6%',
          glutenfree: false,
        },
      ],
      headers: [
        {
          text: 'Dessert (100g serving)',
          align: 'start',
          sortable: true,
          value: 'name',
        },
        { text: 'Calories', value: 'calories', sortable: false},
        { text: 'Fat (g)', value: 'fat', sortable: false },
        { text: 'Carbs (g)', value: 'carbs', sortable: false },
        { text: 'Protein (g)', value: 'protein', sortable: false },
        { text: 'Iron (%)', value: 'iron', sortable: false },
        { text: 'Gluten-Free', value: 'glutenfree', sortable: false },
      ],
    }
  },
}
</script>
