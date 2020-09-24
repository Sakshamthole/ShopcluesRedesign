
<template>
<v-container>
    <v-row no-gutters>
    <v-col
    v-for="i in 3"
    :key=i
    cols="12"
    md="4"
    >

      <v-card
        class=" red lighten-1 mx-2 pa-3"
      >
       <v-img
          src="BMW.png"
          height="300px"
          width="600px"
          >
        </v-img>
        <v-card-text>
          MMH
        </v-card-text>
      </v-card>
      

    </v-col>
    </v-row>

  <v-row
    
    >
    <v-col
    
    
    >
 </v-card>
      <v-img
          src="car2.jpg"
          height="300px"
          width="600px"
          >
        </v-img>
      <v-card
        class="purple lighten-3 pa-12 ma-8"
        <v-img
          src="car.jpg"
          height="200px"
          width="600px"
          >
        </v-img>

    </v-col>
     <v-col
     
    
    >

      <v-card
        class="purple lighten-3 pa-2 ma-2"
      >
        <v-card-text>
          HMM
        </v-card-text>
      </v-card>

    </v-col>
      <v-col md="3">
    <v-card>
        <v-img
          src="BMW.png"
          >
        </v-img>
    </v-card>
  </v-col>
    </v-row>
</v-container>
  </template>
