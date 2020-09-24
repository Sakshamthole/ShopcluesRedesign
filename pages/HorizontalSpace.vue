
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

      <v-card
        class="purple lighten-3"
      >
        <v-card-text>
          HMM
        </v-card-text>
      </v-card>

    </v-col>
     <v-col
     
    
    >

      <v-card
        class="purple lighten-3 ml-n12"
      >
        <v-card-text>
          HMM
        </v-card-text>
      </v-card>

    </v-col>
    </v-row>
</v-container>
  </template>
