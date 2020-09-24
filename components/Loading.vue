<template>
  <v-card
    :loading="loading"
    class="mx-auto my-12"
    max-width="374"
  >
    <v-img
      height="250" 
     
      src="https://cdn.vuetifyjs.com/images/cards/cooking.png"       
    > <!-- added image with height 250 --> 
    </v-img>

    <v-card-title>Cafe Badilico</v-card-title> <!-- title of the card -->

    <v-card-text>
      <v-row
        align="center"
        class="mx-0"
      >
        <v-rating
          :value="4.5"
          color="orange" 
          dense
          half-increments
          readonly
          size="14"
        >
        <!--ratings colour and size-->
        </v-rating>

        <div class="grey--text ml-4">4.5 (413)</div> <!-- Grey colour to value and number of ratings -->
      </v-row>

      <div class="my-4 subtitle-1">
        $ • Italian, Cafe
      </div>

      <div>Small plates, salads & sandwiches - an intimate setting with 12 indoor seats plus patio seating.</div>
    </v-card-text>

    <v-divider class="mx-4"></v-divider>

    <v-card-title>Tonight's availability</v-card-title>

    <v-card-text>
      <v-chip-group
        v-model="selection"
        active-class="deep-purple accent-4 white--text" 
         column
      > <!--purple colour to the time boxes-->
        <v-chip>5:30PM</v-chip>

        <v-chip>7:30PM</v-chip>

        <v-chip>8:00PM</v-chip>

        <v-chip>9:00PM</v-chip>
      </v-chip-group>
    </v-card-text>

    <v-card-actions>
      <v-btn
        color="deep-purple lighten-2"
        text
        @click="reserve" 
      >
      <!-- click on the word Reserve -->
        Reserve
      </v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
  export default {
    data: () => ({
      loading: false,
      //no loading initially  
      selection: 2, 
      //8 pm selected initially
    }),

    methods: {
      reserve () {
        this.loading = true

        setTimeout(() => (this.loading = false), 2000) //loading occurs for 2 seconds when clicked on reserve
      },
    },
  }
</script>